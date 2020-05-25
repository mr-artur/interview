# Java 9
+ [Что нового появилось в Java 9?](#Что-нового-появилось-в-Java-9)
+ [Приватные методы в интерфейсах](#Приватные-методы-в-интерфейсах)
    + [Зачем нужны приватные методы в интерфейсах ?](#Зачем-нужны-приватные-методы-в-интерфейсах)
    + [Пример использования приватного метода в интерфейсе](#Пример-использования-приватного-метода-в-интерфейсе)
+ [Фабричные методы для создания `unmodifiable` коллекций](#Фабричные-методы-для-создания-unmodifiable-коллекций)
    + [`List.of`](#Listof)
    + [`Set.of`](#Setof)
    + [`Map.of`](#Mapof)
+ [Изменение внутреннего представления строк в `String`](#Изменение-внутреннего-представления-строк-в-String)
+ [Новые методы в `Stream` API](#Новые-методы-в-Stream-API)
    + [`takeWhile`](#takeWhile)
    + [`dropWhile`](#dropWhile)
    + [`iterate`](#iterate)
+ [Новые методы в `Optional`](#Новые-методы-в-Optional) 
    + ([`ifPresentOrElse`](#ifPresentOrElse))
    + ([`or`](#or))
    + ([`stream`](#stream))
    
## Что нового появилось в Java 9?
+ Приватные методы в интерфейсах ([_перейти_](#Приватные-методы-в-интерфейсах))
+ Фабричные методы для коллекций, создающие `unmodifiable` экземпляры ([_перейти_](#Фабричные-методы-для-создания-unmodifiable-коллекций))
    + `List.of` ([_перейти_](#Listof))
    + `Set.of` ([_перейти_](#Setof))
    + `Map.of` ([_перейти_](#Mapof))
+ Модули
+ JShell
+ Изменение внутреннего представления строк (`String`) ([_перейти_](#Изменение-внутреннего-представления-строк-в-String))
+ Изменение сборщика мусора по умолчанию (Им был _Parallel GC_, теперь дефолтным стал _G1 (Garbage first_) ).
+ Добавлена возможность использовать effectively-final переменные в `try-with-resources`
+ Добавлены новые методы в `Stream` : ([_перейти_](#Новые-методы-в-Stream-API)) 
    + `takeWhile` ([_перейти_](#takeWhile))
    + `dropWhile` ([_перейти_](#dropWhile))
    + `iterate` ([_перейти_](#iterate))
+ Добавлены новые методы в `Optional` : ([_перейти_](#Новые-методы-в-Optional)) 
    + `ifPresentOrElse` ([_перейти_](#ifPresentOrElse))
    + `or` ([_перейти_](#or))
    + `stream` ([_перейти_](#stream))
+ `ProcessHandle` - API для управления процессами
+ `StackWalker` - класс, представляющий работу со стектрейсами без создания объектов `Exception`
+ `CompletableFuture`

[к оглавлению](#Java-9)

## Приватные методы в интерфейсах
В Java 9 появилась возможность создавать `private` методы в интерфейсах.

Приватные методы не будут видны в реализациях, а поэтому единственное их применение - это использование в `default` методах интерфейса, которые были добавлены в Java 8.

[к оглавлению](#Java-9)

#### Зачем нужны приватные методы в интерфейсах ?
+ Для вынесения дублирующегося кода из `default` - методов
+ Улучшают читаемость
+ Чтобы не было огромных `default` методов
+ Для описания тех фрагментов кода, которые не нужны в наследниках, а нужны только в `default` методах

[к оглавлению](#Java-9)

#### Пример использования приватного метода в интерфейсе
```java
public interface Monster {
 
    int getArmor();
 
    // Наш приватный метод, видимый только в интерфейсе
    private int calculateHit(int damage, int armor) {
        int result = damage - armor;
        return Math.max(result, 0);
    }
 
    // default-метод
    default int calculateHit(int damage) {
        return calculateHit(damage, getArmor());
    }
}

public class Daemon implements Monster {
    public int getArmor() {
        return 2;
    }
}

public class Main {
    public static void main(String[] args) {
        Daemon daemon = new Daemon();
        System.out.println(daemon.calculateHit(3));
    }
}
```
В данном примере мы определили интерфейс с одним абстрактным, одним дефолтным и одним приватным методами и реализации этого интерфейса с переопределением абстрактного метода. При этом в реализации виден дефолтный метод, но не приватный. Дальше написан пример использования реализации в `main`.

[к оглавлению](#Java-9)

## Фабричные методы для создания `unmodifiable` коллекций
В Java 9 добавлены новые статические фабричные методы для основных интерфейсов коллекций.

+ Добавлены методы `List.of`, `Set.of`, `Map.of`, которые возвращают неизменяемые коллекции.
+ Если в любой из этих новых методов передать параметром `null`, то выбросится `NullPointerException`, потому что там везде внутри идет проверка через `Object.requireNonNull()`.
+ Если попытаться вызвать какую-либо модифицирующую операцию на таких коллекциях, будет выброшено `UnsupportedOperationException`.

### `List.of`
Метод `List.of` возвращает неизменяемый список, пустой или с переданными элементами внутри.

Если попытаться вызвать какую-либо модифицирующую операцию на таком созданном списке, будет выброшено `UnsupportedOperationException`.
```java
static <E> List<E> of(E... elements) {
    switch (elements.length) { // implicit null check of elements
        case 0:
            @SuppressWarnings("unchecked")
            var list = (List<E>) ImmutableCollections.ListN.EMPTY_LIST;
            return list;
        case 1:
            return new ImmutableCollections.List12<>(elements[0]);
        case 2:
            return new ImmutableCollections.List12<>(elements[0], elements[1]);
        default:
            return new ImmutableCollections.ListN<>(elements);
    }
}
```
До Java 8 включительно неизменяемый список надо было создавать вот так :
```java
List<String> list1 = new ArrayList<>();
list1.add("Vasya");
list1.add("Petya");
List<String> unmodifiableList1 = Collections.unmodifiableList(list1);
```
Теперь же можно воспользоваться методом `List.of` :
```java
List<String> unmodifiableList = List.of("Vasya", "Petya");
```

[к оглавлению](#Java-9)

### `Set.of`
Метод `Set.of` возвращает неизменяемое множество, пустое или с переданными элементами внутри.

Если попытаться вызвать какую-либо модифицирующую операцию на таком созданном множестве, будет выброшено `UnsupportedOperationException`.
```java
static <E> Set<E> of(E... elements) {
    switch (elements.length) { // implicit null check of elements
        case 0:
            @SuppressWarnings("unchecked")
            var set = (Set<E>) ImmutableCollections.SetN.EMPTY_SET;
            return set;
        case 1:
            return new ImmutableCollections.Set12<>(elements[0]);
        case 2:
            return new ImmutableCollections.Set12<>(elements[0], elements[1]);
        default:
            return new ImmutableCollections.SetN<>(elements);
    }
}
```
До Java 8 включительно неизменяемое множество надо было создавать вот так :
```java
Set<String> set1 = new HashSet<>();
set1.add("Vasya");
set1.add("Petya");
Set<String> unmodifiableSet1 = Collections.unmodifiableSet(set1);
```
Теперь же можно воспользоваться методом `List.of` :
```java
Set<String> unmodifiableSet = Set.of("Vasya", "Petya");
```

[к оглавлению](#Java-9)

### `Map.of`
Метод `Map.of` возвращает неизменяемую мапу, пустую или с переданными парами ключ-значение внутри.

Если попытаться вызвать какую-либо модифицирующую операцию на такой созданной мапе, будет выброшено `UnsupportedOperationException`.
```java
static <K, V> Map<K, V> of(K k1, V v1, K k2, V v2) {
    return new ImmutableCollections.MapN<>(k1, v1, k2, v2);
}
```
До Java 8 включительно неизменяемое множество надо было создавать вот так :
```java
Map<String, String> map1 = new HashMap<>();
map1.put("id1", "Vasya");
map1.put("id2", "Petya");
Map<String, String> unmodifiableMap1 = Collections.unmodifiableMap(map1);
```
Теперь же можно воспользоваться методом `List.of` :
```java
Map<String, String> unmodifiableMap = Map.of("id1", "Vasya", "id2", "Petya");
```

[к оглавлению](#Java-9)

## Изменение внутреннего представления строк в `String`
До Java 9 внутри иммутабельного класса `String` находился массив `char` :
```java
private final char[] value;
```
Теперь же тип массива элементов изменили на `byte` :
```java
private final byte[] value;
```
А также добавили поле `coder`, которое отвечает за кодировку :
```java
private final byte coder;
```
Таким образом, удалось достичь того, что строки занимают меньше места, за счет удаления тех нулевых битов, которые хранились в переменных типа `char`.

Работает это так, что если строка содержит символы, которым нужно не более `8` бит, то кодировка будет `LATIN-1`.
Если же хоть один символ не попадает в диапазон таких, которым нужно не более `8` байт, то выбранная кодировка будет `UTF-16`.

[к оглавлению](#Java-9)

## Новые методы в `Stream` API
В Java 9 были добавлены новые методы в интерфейс `Stream` : 
+ `takeWhile` - выбирает элементы из потока до тех пор, пока условие выполняется
+ `dropWhile` - выбрасывает элементы из потока до тех пор, пока условие не выполнится
+ `iterate` - позволяет заменить цикл `for` стримом

[к оглавлению](#Java-9)

### `takeWhile`
Метод `takeWhile` выбирает элементы из потока до тех пор, пока все они соответствуют условию, и возвращает новый поток с ними внутри. 

Сигнатура метода `takeWhile` в интерфейсе `Stream` : 
```java
default Stream<T> takeWhile(Predicate<? super T> predicate);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию.

Ниже приведен пример использования `takeWhile`.
```java
List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
    .stream()
    .takeWhile(str -> str.length < 4)
    .forEach(System.out::println);

// "ccc"
```

[к оглавлению](#Java-9)

### `dropWhile`
Метод `drowWhile` выбрасывает элементы из потока, пока соблюдается условие для каждого конкретного элемента, и возвращает новый поток с оставшимися элементами

Сигнатура метода `dropWhile` в интерфейсе `Stream` : 
```java
default Stream<T> dropWhile(Predicate<? super T> predicate);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию.

Ниже приведен пример использования `dropWhile`.
```java
IntStream.range(1, 10).dropWhile(x -> x < 5).forEach(System.out::print) // 56789
```

[к оглавлению](#Java-9)

### `iterate`
Метод `iterate` Позволяет заменить циклы стримами. В нем нужно задать изначальный элемент, предикат - условие остановки цикла и функцию для получения следующего элемента из предыдущего.

Сигнатуры метода `iterate` в интерфейсе `Stream` : 
```java
static<T> Stream<T> iterate(T seed, Predicate<? super T> hasNext, UnaryOperator<T> next);

static<T> Stream<T> iterate(final T seed, final UnaryOperator<T> f);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию.

Ниже приведен пример использования `iterate`.
```java
IntStream.iterate(0, x -> x < 3, x -> x + 1).forEach(System.out::print) // 012
```

[к оглавлению](#Java-9)

## Новые методы в `Optional`
В Java 9 в класс `Optional` были добавлены `3` новых метода :
+ `ifPresentOrElse` - принимает `2` действия, первое будет выполнено если опциональное значение присутствует, второе - если его нету.
+ `or` - позволяет не делать лишние проверки на `isPresent()`, позволяет в одну цепочку связывать разные `Optional`. Если все опциональные значения в цепочке пустые, вернет последнее из них.
+ `stream` - преобразовывание опционального значения в стрим, который будет содержать не более одного элемента. Это может пригодиться, если нам нужен lazy стрим.

[к оглавлению](#Java-9)

### `ifPresentOrElse`
В Java 8, можно было определить поведение только для случая, когда значение `Optional` существует. В Java 9 стало возможно указать две разных функции, определяющих что делать, если значение существует, и если не существует.

Сигнатура метода `ifPresentOrElse` в классе `Optional` : 
```java
void ifPresentOrElse(Consumer<? super T> action, Runnable emptyAction);
```

Ниже приведен пример использования `ifPresentOrElse`.
```java
jshell> Optional.empty().ifPresentOrElse(x -> System.out.println(x), () -> System.out.println("empty"));
empty
```

[к оглавлению](#Java-9)

### `or`
В Java 9 добавлен метод `or`, который позволяет связывать `Optional` в цепочки, при этом не используя `ifPresent`.

Сигнатура метода `or` в классе `Optional` : 
```java
Optional<T> or(Supplier<? extends Optional<? extends T>> supplier);
```

Ниже приведен пример использования `or`.
```java
jshell> Optional.empty().or(() -> Optional.of("NotEmpty"))
$5 ==> Optional[NotEmpty]
```

[к оглавлению](#Java-9)

### `stream`
В Java 9 добавлен метод `stream`, который позволяет получить синглтоновый стрим из опционального значения. В зависимости от присутствия значения, в стриме будет либо `0`, либо `1` значение. Это можно использовать для _lazy_ операций со значением, потому что в таком стриме они не будут выполняться сразу, что видно на примере ниже.

Сигнатура метода `or` в классе `Optional` : 
```java
Optional<T> or(Supplier<? extends Optional<? extends T>> supplier);
```

Ниже приведен пример использования `stream`, операции с которым работают по _lazy_ подходу.
```java
jshell> Optional.of(1).map(x -> x * 3)
$10 ==> Optional[3]

jshell> Optional.of(1).stream().map(x -> x * 3)
$11 ==> java.util.stream.ReferencePipeline$3@67b92f0a
```

[к оглавлению](#Java-9)
