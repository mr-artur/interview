# Java 9
+ [Что нового появилось в Java 9?](#Что-нового-появилось-в-Java-9)
+ [Приватные методы в интерфейсах](#Приватные-методы-в-интерфейсах)
    + [Зачем нужны приватные методы в интерфейсах ?](#Зачем-нужны-приватные-методы-в-интерфейсах)
    + [Пример использования приватного метода в интерфейсе](#Пример-использования-приватного-метода-в-интерфейсе)
+ [Фабричные методы для создания `unmodifiable` коллекций](#Фабричные-методы-для-создания-unmodifiable-коллекций)
    + [`List.of`](#List-of)
    + [`Set.of`](#Set-of)
    + [`Map.of`](#Map-of)
+ [Изменение внутреннего представления строк в `String`](#Изменение-внутреннего-представления-строк-в-String)

## Что нового появилось в Java 9?
+ Приватные методы в интерфейсах ([_перейти_](#Приватные-методы-в-интерфейсах))
+ Фабричные методы для коллекций, создающие `unmodifiable` экземпляры ([_перейти_](#Фабричные-методы-для-создания-unmodifiable-коллекций))
+ Модули
+ JShell
+ Изменение внутреннего представления строк (`String`) ([_перейти_](#Изменение-внутреннего-представления-строк-в-String))
+ Изменение сборщика мусора по умолчанию
+ Добавлена возможность использовать effectively-final переменные в `try-with-resources`
+ Добавлены новые методы в `Stream` API
+ Добавлены новые методы в `Optional`
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


