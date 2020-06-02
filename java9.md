# Java 9
+ [Что нового появилось в Java 9?](#Что-нового-появилось-в-Java-9)
+ [Приватные методы в интерфейсах](#Приватные-методы-в-интерфейсах)
    + [Зачем нужны приватные методы в интерфейсах ?](#Зачем-нужны-приватные-методы-в-интерфейсах)
    + [Пример использования приватного метода в интерфейсе](#Пример-использования-приватного-метода-в-интерфейсе)
+ [Фабричные методы для создания `unmodifiable` коллекций](#Фабричные-методы-для-создания-unmodifiable-коллекций)
    + [`List.of`](#Listof)
    + [`Set.of`](#Setof)
    + [`Map.of`](#Mapof)
+ [Модули](#Модули)
+ [JShell](#JShell)
+ [Изменение внутреннего представления строк в `String`](#Изменение-внутреннего-представления-строк-в-String)
+ [Изменение сборщика мусора по умолчанию на _G1_](#Изменение-сборщика-мусора-по-умолчанию-на-G1)
+ [_Effectively-final_ переменные в `try-with-resources`](#Effectively-final-переменные-в-try-with-resources)
+ [Новые методы в `Stream` API](#Новые-методы-в-Stream-API)
    + [`takeWhile`](#takeWhile)
    + [`dropWhile`](#dropWhile)
    + [`iterate`](#iterate)
+ [Новые методы в `Optional`](#Новые-методы-в-Optional) 
    + ([`ifPresentOrElse`](#ifPresentOrElse))
    + ([`or`](#or))
    + ([`stream`](#stream))
+ [`ProcessHandle`](#ProcessHandle)
+ [`StackWalker`](#StackWalker)

## Что нового появилось в Java 9?
+ Приватные методы в интерфейсах ([_перейти_](#Приватные-методы-в-интерфейсах))
+ Фабричные методы для коллекций, создающие `unmodifiable` экземпляры ([_перейти_](#Фабричные-методы-для-создания-unmodifiable-коллекций))
    + `List.of` ([_перейти_](#Listof))
    + `Set.of` ([_перейти_](#Setof))
    + `Map.of` ([_перейти_](#Mapof))
+ Модули ([_перейти_](#Модули))
+ JShell ([_перейти_](#JShell))
+ Изменение внутреннего представления строк (`String`) ([_перейти_](#Изменение-внутреннего-представления-строк-в-String))
+ Изменение сборщика мусора по умолчанию (Им был _Parallel GC_, теперь дефолтным стал _G1 (Garbage first_) ). ([_перейти_](#Изменение-сборщика-мусора-по-умолчанию-на-G1))
+ Добавлена возможность использовать effectively-final переменные в `try-with-resources` ([_перейти_](#Effectively-final-переменные-в-try-with-resources))
+ Добавлены новые методы в `Stream` : ([_перейти_](#Новые-методы-в-Stream-API)) 
    + `takeWhile` ([_перейти_](#takeWhile))
    + `dropWhile` ([_перейти_](#dropWhile))
    + `iterate` ([_перейти_](#iterate))
+ Добавлены новые методы в `Optional` : ([_перейти_](#Новые-методы-в-Optional)) 
    + `ifPresentOrElse` ([_перейти_](#ifPresentOrElse))
    + `or` ([_перейти_](#or))
    + `stream` ([_перейти_](#stream))
+ `ProcessHandle` - API для управления процессами ([_перейти_](#ProcessHandle))
+ `StackWalker` - класс, представляющий работу со стектрейсами без создания объектов `Exception` ([_перейти_](#StackWalker))
+ Новые методы для многопоточного класса `CompletableFuture` :
    + `copy`
    + `completeInTimeout`

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

## Модули
+ Модули - это новый уровень инкапсуляции в Java 9.
+ Модуль - это группа пакетов или ресурсов, объединенных в одно целое и к которым можно обращаться по имени модуля.
+ Модуль обычно состоит из группы пакетов.
+ Одна из главных фишек инкапсуляции модуля - это то, что его элементы (классы, например) недоступны для рефлексии.
+ В качестве названия модуля может применяться любой идентификатор из алфавитно-цифровых символов и подчеркиваний.
+ Рекомендуется, чтобы название модуля соответствовало названию, с которого начинаются пакеты этого модуля.
+ В модуле должен быть _дескриптор модуля_ `module-info.java`.

Подробнее о модулях с примером кода [тут](https://urvanov.ru/2018/03/13/модульность-в-java-9-с-jigsaw/).

Подробнее о модулях с примером кода и скрином структуры проекта [тут](https://metanit.com/java/tutorial/11.1.php).

[к оглавлению](#Java-9)

## JShell
_JShell_ - это интерпретатор комманд Java. С помощью него можно набирать куски Java кода.

Его можно найти в каталоге `bin` дистрибутива Java.

Базовые примеры написания кода в JShell :
```java
jshell> System.out.println("Hello, World!");
Hello, World!
```
Можно даже так (в этом случае интерпретатор неявно создаст переменную $2):
```java
jshell> 2 + 10
$2 ==> 12
```
JShell также имеет свои команды :
```java
jshell> /help
|  Type a Java language expression, statement, or declaration.
|  Or type one of the following commands:
|  /list [<name or id>|-all|-start]
|  	list the source you have typed
|  /edit <name or id>
|  	edit a source entry referenced by name or id
|  /drop <name or id>
|  	delete a source entry referenced by name or id
|  /save [-all|-history|-start] <file>
|  	Save snippet source to a file.
|  /open <file>
|  	open a file as source input
|  /vars [<name or id>|-all|-start]
|  	list the declared variables and their values
|  /methods [<name or id>|-all|-start]
|  	list the declared methods and their signatures
|  /types [<name or id>|-all|-start]
|  	list the declared types
|  /imports 
|  	list the imported items
|  /exit 
|  	exit jshell
|  /env [-class-path <path>] [-module-path <path>] [-add-modules <modules>] ...
|  	view or change the evaluation context
|  /reset [-class-path <path>] [-module-path <path>] [-add-modules <modules>]...
|  	reset jshell
|  /reload [-restore] [-quiet] [-class-path <path>] [-module-path <path>]...
|  	reset and replay relevant history -- current or previous (-restore)
|  /history 
|  	history of what you have typed
|  /help [<command>|<subject>]
|  	get information about jshell
|  /set editor|start|feedback|mode|prompt|truncation|format ...
|  	set jshell configuration information
|  /? [<command>|<subject>]
|  	get information about jshell
|  /! 
|  	re-run last snippet
|  /<id> 
|  	re-run snippet by id
|  /-<n> 
|  	re-run n-th previous snippet
|  
|  For more information type '/help' followed by the name of a
|  command or a subject.
|  For example '/help /list' or '/help intro'.
|  
|  Subjects:
|  
|  intro
|  	an introduction to the jshell tool
|  shortcuts
|  	a description of keystrokes for snippet and command completion,
|  	information access, and automatic code generation
|  context
|  	the evaluation context options for /env /reload and /reset
 
jshell> 
```

[Подробнее про JShell](https://urvanov.ru/2017/11/13/java-9-jshell/)

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

## Изменение сборщика мусора по умолчанию на _G1_
+ До Java 9 сборщиком мусора по умолчанию был _Parallel GC_, но теперь по умолчанию был выбран _G1_.
+ _Parallel GC_ оперирует только поколениями, тогда как _G1_, помимо них, работает с регионами.
+ _G1_ направлен на уменьшение _latency_ (маленькие отдельные паузы), выполняя часть сборки вне Stop-the-world(время, когда сборщик мусора останавливает работу приложения).

Подробнее о _G1_ [тут](https://urvanov.ru/2018/03/25/сборщик-мусора-g1-в-java-9/).

Также о _G1_ и остальных сборщиках [тут](https://itsobes.ru/JavaSobes/kak-rabotaet-sborka-musora/).

[к оглавлению](#Java-9)

## _Effectively-final_ переменные в `try-with-resources`
В Java 9 была добавлена возможность использовать в конструкции `try-with-resources` "фактически финальные" переменные, которые инициализированы раньше ресурсного блока `try-with-resources`.

_Effectively final переменные_ - это такие, которые не имеют модификатор доступа `final`, но при этом мы с ними работаем как с финальными в коде.

Пример с использованием фактически финальной переменной в `try-with-resouces` :
```java
boolean a() throws Exception { 
  Socket s = new Socket(); 
  try (s) { } 
  return s.isClosed();
}
```
После выполнения блока `try` сокет `s` будет закрыт.

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

## `ProcessHandle`
В Java 9 был добавлен класс для управления процессами - `ProcessHandle`.

Он предоставляет API для анализа текущего процесса, других процессов, найденных по pid, их дочерних процессов и т.д.

Пример использования `ProcessHandle` представлен ниже :
```java
jshell> ProcessHandle current = ProcessHandle.current();
current ==> 6349

jshell> current.pid()
$33 ==> 6349

jshell> current.info().\TAB
arguments()          command()            commandLine()        equals(              getClass()
hashCode()           notify()             notifyAll()          startInstant()       toString()
totalCpuDuration()   user()               wait(

jshell> current.info().command()
$34 ==> Optional[/Library/Java/JavaVirtualMachines/jdk-9.jdk/Contents/Home/bin/java]
```
Как видно на примере, у процесс хендла есть такие основные функции, как получение коммандной строки, а также аргументов, которые были использованы для запуска процесса, но остальные фичи также достойны внимания.

Также в Java 9 теперь можно удобно запускать код после того, как процесс завершился. Для этого был добавлен следующий метод :
```java
CompletableFuture<Process> onExit();
```

[к оглавлению](#Java-9)

## `StackWalker`
`StackWalker` - это новый добавленный класс в Java 9, который позволяет просматривать стек вызовов без выброса `Exception` - ов для этого.

`StackWalker` дает возможность бродить по стеку, фильтровать его, и эффективно делать многие другие вещи.

В примере снизу происходит выбор `5` верхних элементов стектрейса :
```java
jshell> StackWalker.getInstance().walk(s -> s.limit(5).collect(Collectors.toList()));
$36 ==> [do_it$(java:36), 
jdk.jshell/jdk.jshell.execution.DirectExecutionControl.invoke(DirectExecutionControl.java:209), 
jdk.jshell/jdk.jshell.execution.RemoteExecutionControl.invoke(RemoteExecutionControl.java:116), 
jdk.jshell/jdk.jshell.execution.DirectExecutionControl.invoke(DirectExecutionControl.java:119), 
jdk.jshell/jdk.jshell.execution.ExecutionControlForwarder.processCommand(ExecutionControlForwarder.java:134)]
```

[к оглавлению](#Java-9)
