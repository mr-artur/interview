# Java 8
+ [Что нового появилось в Java 8?](#Что-нового-появилось-в-Java-8)
+ [Методы интерфейсов по умолчанию](#Методы-интерфейсов-по-умолчанию)
    + [Пример метода интерфейса по умолчанию](#Пример-метода-интерфейса-по-умолчанию)
+ [Лямбда-выражение](#Лямбда-выражение)
    + [Пример использования лямбда-выражения](#Пример-использования-лямбда-выражения)
    + [Ограничения доступа к переменным из лямбд](#Ограничения-доступа-к-переменным-из-лямбд)
    + [Ограничения доступа к методам из лямбд](#Ограничения-доступа-к-методам-из-лямбд)
+ [Функциональный интерфейс](#Функциональный-интерфейс)
    + [Аннотация `@FunctionalInterface`](#Аннотация-FunctionalInterface)
    + [Пример `@FunctionalInterface`](#Пример-FunctionalInterface)    
    + [`Predicate`](#Predicate)  
        + [Пример `Predicate`](#Пример-Predicate)  
        + [Пример `Predicate` с `negate()`](#Пример-Predicate-с-negate)  
    + [`Function`](#Function)   
        + [Пример `Function`](#Пример-Function)  
        + [Пример `Function` с `andThen()`](#Пример-Function-с-andThen)
    + [`Supplier`](#Supplier)   
        + [Пример `Supplier`](#Пример-Supplier) 
    + [`Consumer`](#Consumer)  
        + [Пример `Consumer`](#Пример-Consumer) 
    + [`Comparator`](#Comparator)  
        + [Пример `Comparator`](#Пример-Comparator)
+ [Ссылки на методы и конструкторы](#Ссылки-на-методы-и-конструкторы)
+ [`Optional`](#Optional)
    + [Пример `Optional`](#Пример-Optional)
    + [Пример `Optional` с `orElseThrow()`](#Пример-Optional-с-orElseThrow)
+ [Streams](#Streams)
    + [`Filter`](#Filter)
    + [`Sorted`](#Sorted)
    + [`Map`](#Map)
    + [`FlatMap`](#FlatMap)
    + [`Match`](#Match)
    + [`Count`](#Count)
    + [`Reduce`](#Reduce)
    + [`Collect`](#Collect)
    + [Parallel Streams](#Parallel-Streams)
    + [Метод `Collection.stream()`](#Метод-Collection-stream)
    + [Метод `Collection.parallelStream()`](#Метод-Collection-parallel-stream) 
+ [Новые методы `Map`](#Новые-методы-Map)
    + [`getOrDefault`](#getOrDefault)
    + [`forEach`](#forEach)
    + [`replaceAll`](#replaceAll)
    + [`putIfAbsent`](#putIfAbsent)
    + [`remove`](#remove)
    + [`replace`](#replace)
    + [`computeIfAbsent`](#computeIfAbsent)
    + [`computeIfPresent`](#computeIfPresent)
    + [`compute`](#compute)
    + [`merge`](#merge)
+ [Оптимизация корзин в `HashMap`](#Оптимизация-корзин-в-HashMap)
+ [Новый API для работы со временем и датами](#Новый-API-для-работы-со-временем-и-датами)
    + [`Clock` и `Instant`](#Clock-и-Instant)
    + [`ZoneId`](#ZoneId)
    + [`LocalTime`](#LocalTime)
    + [`LocalDate`](#LocalDate)
    + [`LocalDateTime`](#LocalDateTime)
+ [Повторяемые аннотации](#Повторяемые-аннотации)

## Что нового появилось в Java 8?
+ Методы интерфейсов по умолчанию ([_перейти_](#Методы-интерфейсов-по-умолчанию))
+ Лямбда-выражения ([_перейти_](#Лямбда-выражения)) со своими ограничениями доступа к переменным ([_перейти_](#Ограничения-доступа-к-переменным-из-лямбд)) и методам ([_перейти_](#Ограничения-доступа-к-методам-из-лямбд)) 
+ Функциональные интерфейсы ([_перейти_](#Функциональный-интерфейс)), в т.ч., встроенные функциональные интерфейсы :
    + `Predicate` ([_перейти_](#Predicate))
    + `Function` ([_перейти_](#Function))
    + `Supplier` ([_перейти_](#Supplier))
    + `Consumer` ([_перейти_](#Consumer))
    + `Comparator` (стал функциональным) ([_перейти_](#Comparator))
    + `Runnable` (стал функциональным)
+ Ссылки на методы и конструкторы ([_перейти_](#Ссылки-на-методы-и-конструкторы))
+ _Optionals_ - опциональные значения ([_перейти_](#Optional))
+ Потоки элементов - Streams ([_перейти_](#Streams)), как последовательные, так и параллельные ([_перейти_](#Parallel-Streams)), и имеющие большой набор методов, основные из которых :
    + `filter` ([_перейти_](#Filter))
    + `sorted` ([_перейти_](#Sorted))
    + `map` ([_перейти_](#Map))
    + `flatMap` ([_перейти_](#FlatMap))
    + `match` ([_перейти_](#Match))
    + `count` ([_перейти_](#Count))
    + `reduce` ([_перейти_](#Reduce))
    + `collect` ([_перейти_](#Collect))

    Также у коллекций появились такие методы для создания потока элементов как :
    + `stream` ([_перейти_](#Метод-Collection-stream))
    + `parallelStream` ([_перейти_](#Метод-Collection-parallelStream))
+ Новые методы для `Map` - ассоциативных массивов ([_перейти_](#Новые-методы-Map))
+ Оптимизация корзин в `HashMap` ([_перейти_](#Оптимизация-корзин-в-HashMap))
+ Новый API для работы со временем и датами : ([_перейти_](#Новый-API-для-работы-со-временем-и-датами))
    + `Clock` и `Instant` - работа с текущими датой и временем ([_перейти_](#Сlock-и-Instant))
    + `ZoneId` - часовые пояса ([_перейти_](#ZoneId))
    + `LocalTime` - работа со временем с учетом часового пояса ([_перейти_](#LocalTime))
    + `LocalDate` - работа с конкретными датами ([_перейти_](#LocalDate))
    + `LocalDateTime` - работа и с временем, и с датой ([_перейти_](#LocalDateTime))
+ Повторяемые аннотации ([_перейти_](#Повторяемые-аннотации))

[к оглавлению](#Java-8)

## Методы интерфейсов по умолчанию
В Java 8 появилась поддержка методов по умолчанию для интерфейсов.

_Методы по умолчанию_ - это такие методы, которые в интерфейсе имеют реализацию. Обозначаются они ключевым словом `default`. Также они известны, как методы расширения.

[к оглавлению](#Java-8)

#### Пример метода интерфейса по умолчанию
Объявление интерфейса с дефолтным методом :
```java
interface Formula {

    double calculate(int a);

    default double sqrt(int a) {
        return Math.sqrt(a);
    }
}
```
В данном интерфейсе `Formula`, помимо абстрактного метода `calculate(int a)`, также определен метод по умолчанию `sqrt`. Таким образом, классы, реализующие этот интерфейс, должны будут переопределить только первый метод, а второй уже будет присутствовать в их экземплярах.

Использование такого интерфейса :
```java
Formula formula = new Formula() {
    @Override
    public double calculate(int a) {
        return sqrt(a * 100);
    }
};

formula.calculate(100);     // 100.0
formula.sqrt(16);           // 4.0
```
Как видно в данном примере использования интерфейса с методом по умолчанию, мы создаем анонимную его реализацию, переопределяя только первый метод таким образом, что он использует дефолтный метод реализуемого интерфейса. Этот код является довольно избыточным, поэтому далее будет рассмотрен способ короткой записи анонимных реализаций, введенный в Java 8.

[к оглавлению](#Java-8)

## Лямбда-выражение
_Лямбда выражение_ - это реализация метода, сигнатура которого находится в функциональном интерфейсе. Простыми словами - это набор действий, который можно сохранить в переменную и использовать много раз. Также можно сказать, что это ссылка на метод, которая теперь записыватеся более коротко. То есть, это по сути то же создание объекта анонимной реализации функционального интерфейса.

[к оглавлению](#Java-8)

#### Пример использования лямбда-выражения
Возьмем пример сортировки строк, который использовался в предыдущих версиях языка :
```java
List<String> names = Arrays.asList("peter", "anna", "mike", "ksenia");

Collections.sort(names, new Comparator<String>() {
    @Override
    public int compare(String a, String b) {
        return b.compareTo(a);
    }
});
```
Тут мы создаем анонимный компаратор, для того чтобы передать его вторым аргументов в функцию сортировки.

В Java 8 же с помощью лямбды мы можем записать тоже самое в более коротком виде :
```java
Collections.sort(names, (String a, String b) -> {
    return b.compareTo(a);
});
```
Как видим, метод стал короче и читабельнее. Далее, можно сделать его еще короче, так как в реализации всего одна строка, можно записать ее без фигурных скобок и оператора `return`.
```java
Collections.sort(names, (String a, String b) -> b.compareTo(a));
```
Также можно не писать типы аргументов. Итоговая запись будет выглядеть вот так :
```java
Collections.sort(names, (a, b) -> b.compareTo(a));
```
Как видим, эта запись намного понятнее, короче и читабельнее чем та, что использовалась в предыдущих версиях.

[к оглавлению](#Java-8)

#### Ограничения доступа к переменным из лямбд
+ Доступ к переменным внешней области действия из лямбд схож с доступом из анонимных объектов.
+ Из лямбд можно ссылаться на переменные, объявленные как final, на поля экземпляра, статические поля и effectively final переменные ("фактически финальные" переменные, например, которые не final, но после объявления лямбды им не присваиваются новые значения).
+ Из лямбд можно менять нефинальные поля экземпляра и статические поля.

Данный пример скомпилируется :
```java
final int num = 1;
Converter<Integer, String> stringConverter = (from) -> String.valueOf(from + num);

stringConverter.convert(2);     // 3
```
Но и так (без `final` тоже будет работать) :
```java
int num = 1;
Converter<Integer, String> stringConverter = (from) -> String.valueOf(from + num);

stringConverter.convert(2);     // 3
```
А следующий код НЕ скомпилируется :
```java
int num = 1;
Converter<Integer, String> stringConverter = (from) -> String.valueOf(from + num);
num = 3;
```
В данных примерах внутри лямбды переменную `num` изменять нельзя.

Ниже приведен еще один пример, в котором показана возможность записи значений статических и экземплярных полей из лямбд. Пример успешно будет скомпилирован.
```java
class Lambda4 {
    static int outerStaticNum;
    int outerNum;

    void testScopes() {
        Converter<Integer, String> stringConverter1 = (from) -> {
            outerNum = 23;
            return String.valueOf(from);
        };

        Converter<Integer, String> stringConverter2 = (from) -> {
            outerStaticNum = 72;
            return String.valueOf(from);
        };
    }
}
```

[к оглавлению](#Java-8)

#### Ограничения доступа к методам из лямбд
+ Внутри лямбд нельзя обращаться к методам по умолчанию.

Данный код не скомпилируется :
```java
interface Formula {

    double calculate(int a);

    default double sqrt(int a) {
        return Math.sqrt(a);
    }
}

Formula formula = (a) -> sqrt(a * 100);  // ошибка компиляции : нельзя использовать методы по умолчанию из лямбд
```

[к оглавлению](#Java-8)

## Функциональный интерфейс
_Функциональный интерфейс_ - это такой интерфейс, который может иметь __только один__ абстрактный метод и сколько угодно неабстрактных.
Каждый такой интерфейс может использоваться для лямбда-выражений и таким образом каждой лямбде будет соответствовать тип, представленный таким интерфейсом.

[к оглавлению](#Java-8)

## Аннотация `@FunctionalInterface`
Используется для того, чтобы гарантировать, что наш интерфейс соответствует требованию функционального. 

Работает очень просто - если в интерфейс, аннотированный этой аннотацией, добавить второй абстрактный метод, то компилятор выдаст ошибку.

[к оглавлению](#Java-8)

#### Пример `@FunctionalInterface`
Функциональный интерфейс :
```java
@FunctionalInterface
interface Converter<F, T> {
    T convert(F from);
}
```
Создание и использование лямбды :
```java
Converter<String, Integer> converter = (from) -> Integer.valueOf(from);
Integer converted = converter.convert("123");
System.out.println(converted);      // 123
```
Стоит также заметить, что код работать будет и без аннотации `@FunctionalInterface`. Но она просто дает гарантию, что в интерфейсе всего один абстрактный метод.

[к оглавлению](#Java-8)

## `Predicate`
_Предикаты_ - это функции, принимающие один аргумент любого типа и возвращающие значение типа `boolean`. 

Интерфейс `Predicate` является функциональным, внутри лежит один абстрактный метод `test`.

Сигнатура метода `test` в интерфейсе `Predicate` : 
```java
boolean test(T t);
```

[к оглавлению](#Java-8)

#### Пример `Predicate`
```java
Predicate<String> predicate = (s) -> s.length() > 0;

predicate.test("foo");              // true
```

[к оглавлению](#Java-8)

Интерфейс `Predicate` также имеет`default` - методы, которые позволяют строить сложные условия. Примерами таких методов являются `or()`, `and()`, `negate()`.

#### Пример `Predicate` с `negate()`
```java
Predicate<String> predicate = (s) -> s.length() > 0;

predicate.negate().test("foo");     // false
```

[к оглавлению](#Java-8)

## `Function`
_Функции_ - это такие лямбда-выражения, которые принимают один аргумент и возвращают результат некоего типа. 

Интерфейс `Function` является функциональным, внутри лежит один абстрактный метод `apply`.

Сигнатура метода `apply` в интерфейсе `Function` : 
```java
R apply(T t);
```

[к оглавлению](#Java-8)

#### Пример `Function`
```java
Function<String, Integer> toInteger = Integer::valueOf;

backToString.apply("123");     // 123
```

[к оглавлению](#Java-8)

Интерфейс `Function` также имеет`default` - методы, которые позволяют строить цепочки функций. Примерами таких методов являются `compose`, `andThen`.

#### Пример `Function` с `andThen()`
```java
Function<String, Integer> toInteger = Integer::valueOf;
Function<String, String> backToString = toInteger.andThen(String::valueOf);

backToString.apply("123");     // "123"
```

[к оглавлению](#Java-8)

## `Supplier`
_Поставщики_ - это такие функции, которые не принимают аргументов и возвращают результат некоего типа. 

Интерфейс `Supplier` является функциональным, внутри лежит один абстрактный метод `get`.

Сигнатура метода `get` в интерфейсе `Supplier` : 
```java
T get();
```

[к оглавлению](#Java-8)

#### Пример `Supplier`
```java
Supplier<Person> personSupplier = Person::new;
personSupplier.get();           // new Person
```

[к оглавлению](#Java-8)

## `Consumer`
_Потребители_ - это такие функции, которые принимают один аргумент некоего типа и не возвращают ничего. 

Интерфейс `Consumer` является функциональным, внутри лежит один абстрактный метод `accept`.

Сигнатура метода `accept` в интерфейсе `Consumer` : 
```java
void accept(T t);
```

[к оглавлению](#Java-8)

#### Пример `Consumer`
```java
Consumer<Person> greeter = (p) -> System.out.println("Hello, " + p.firstName);
greeter.accept(new Person("Luke", "Skywalker"));
```

[к оглавлению](#Java-8)

## `Comparator`
_Компараторы_ существовали и в предыдущих версиях Java. В Java 8 же на интерфейс `Comparator` навесили аннотацию `@FunctionalInterface` и добавили ему методы по умолчанию, самые интересные из которых `thenComparing()`, который позволяет строить цепочки компараторов и `reversed()`, который возвращает противоположный компаратор.

В интерфейсе `Comparator` единственный абстрактный метод называется `compare`.

[к оглавлению](#Java-8)

#### Пример `Comparator`
```java
Comparator<Person> comparator = (p1, p2) -> p1.firstName.compareTo(p2.firstName);

Person p1 = new Person("John", "Doe");
Person p2 = new Person("Alice", "Wonderland");

comparator.compare(p1, p2);             // > 0
comparator.reversed().compare(p1, p2);  // < 0
```

[к оглавлению](#Java-8)

## Ссылки на методы и конструкторы
В Java 8 стало возможным передавать ссылки на методы или конструкторы. Делается это с помощью ключевого слова `::`.

Пример ссылки на статический метод :
```java
Converter<String, Integer> converter = Integer::valueOf;
Integer converted = converter.convert("123");
System.out.println(converted);      // 123
```

Пример ссылки на метод экземпляра :
```java
class Something {
    String startsWith(String s) {
        return String.valueOf(s.charAt(0));
    }
}

Something something = new Something();
Converter<String, String> converter = something::startsWith;
String converted = converter.convert("Java");
System.out.println(converted);    // "J"
```

Пример ссылки на конструктор :
```java
class Person {
    private String name;
    
    public Person(String name) {
        this.name = name;
    }   
}

List<Person> guys = List.of("Petr", "Claudii").stream()
    .map(Person::new)
    .collect(Collectors.toList());
```

[к оглавлению](#Java-8)

## `Optional`
`Optional` - это новый класс, добавленный в Java 8, который помогает упростить работу с _nullable_ значениями. Опциональные значения являются удобным способом предотвращения `NullPointerException`. 

По сути это контейнер для значения, которое может быть равно `null`. Например, нам нужен метод, который возвращает какое-то значение, но иногда оно может быть пустым. Раньше надо было бы возвращать null, но это всегда риск попасть в каком-то месте на `NPE`, а поэтому использования `Optional` тут будет очень кстати.

`Optional` является `final` классом, `value` внутри него тоже `final`, но при этом он не совсем _immutable_, так как не все условия иммутабельности соблюдены. Например, геттер возвращает просто `value`, а не копию.

[к оглавлению](#Java-8)

#### Пример `Optional`
```java
Optional<String> optional = Optional.of("bam");

optional.isPresent();           // true
optional.get();                 // "bam"
optional.orElse("fallback");    // "bam"

optional.ifPresent((s) -> System.out.println(s.charAt(0)));     // "b"
```

[к оглавлению](#Java-8)

#### Пример `Optional` с `orElseThrow()`
Одним из частых применений `Optional` является работа с БД, так как, например, при запросе на получение элемента по `id` он не будет обязательно найден. Таким образом возвращается опциональное значение, которые мы можем обработать в сервисе и выбросить исключение, если оно пустое.
```java
@Override
public UserVO findByUsername(String username) {
    return userGateway.findByLogin(username)
        .orElseThrow(() -> new UsernameNotFoundException(String.format("Can't find user with username: %s",
                                                                       username)));
}
```

[к оглавлению](#Java-8)

## Streams
+ _Поток_ - это последовательность элементов, над которой мы можем производить различные операции. Эти операции могут быть промежуточными или терминальными. 
+ Промежуточные операции возвращают поток в качестве результата, а терминальные - что-либо другое или вообще ничего, поэтому они всегда находятся в конце цепочки вызовов.
+ Потоки представлены интерфейсом `Stream`, находящийся в `java.util`. Его расширяют такие интерфейсы, как например `IntStream`, `LongStream`, `DoubleStream`, а также его реализует класс `AbstractPipeline`.
+ Есть такие реализации потока, как `ReferencedPipeline`, `IntPipeline`, `DoublePipeline`, `LongPipeline`.
+ Внутри потоки работают на основе `Spliterator`, у которого есть метод `tryAdvance()`, а также `trySplit()`, который используется для параллельных потоков.
+ Операции над потоками могут выполняться как последовательно, так и параллельно.
+ В Java 8 можно создать поток дефолтными методами `Collection.stream() или Collection.parallelStream()`

Далее будут рассмотрены основные методы потоков.

[к оглавлению](#Java-8)

### `Filter`
Метод `filter` принимает один аргумент - предикат, который фильтрует элементы потока. Те элементы, для которых предикат вернет `true`, останутся в потоке. 

Сигнатура метода `filter` в интерфейсе `Stream` : 
```java
Stream<T> filter(Predicate<? super T> predicate);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию. 

В данном примере мы используем `filter` вместе с терминальной операцией `forEach`.
```java
List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
    .stream()
    .filter((s) -> s.startsWith("a"))
    .forEach(System.out::println);

// "aaa2", "aaa1"
```

[к оглавлению](#Java-8)

### `Sorted`
Метод `sorted` имеет две перегруженные версии :
+ без параметров, в ней элементы сортируются в натуральном порядке 
+ с параметром - компаратором, используя который и будет происходить сортировка

Сигнатуры метода `sorted` в интерфейсе `Stream` : 
```java
Stream<T> sorted();

Stream<T> sorted(Comparator<? super T> comparator);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию. 

Также можно заметить, что `sorted` не меняет последовательность элементов в изначальной коллекции, а меняет только порядок элементов в потоке.

Ниже приведен пример использования`sorted`.
```java
List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
    .stream()
    .sorted()
    .filter((s) -> s.startsWith("a"))
    .forEach(System.out::println);

// "aaa1", "aaa2"
```

[к оглавлению](#Java-8)

### `Map`
Метод `map` преобразовывает каждый элемент потока в другой объект при помощи переданной функции. Новый объект в этом случае может быть как того же, так и другого типа. 

Сигнатура метода `map` в интерфейсе `Stream` : 
```java
<R> Stream<R> map(Function<? super T, ? extends R> mapper);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию.

Ниже приведен пример использования `map`.
```java
List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
    .stream()
    .map(String::toUpperCase)
    .sorted((a, b) -> b.compareTo(a))
    .forEach(System.out::println);

// "DDD2", "DDD1", "CCC", "BBB3", "BBB2", "AAA2", "AAA1"
```

[к оглавлению](#Java-8)

### `FlatMap`
Метод `map` преобразовывает каждый элемент потока в 0 или больше других объектов при помощи переданной функции.

Сигнатура метода `flatMap` в интерфейсе `Stream` : 
```java
<R> Stream<R> flatMap(Function<? super T, ? extends Stream<? extends R>> mapper);
```

Эта операция является промежуточной, так как позволяет после себя вызвать следующую операцию. 

Ниже приведен пример использования `flatMap`.
```java
List<List<Integer>> listOfListofInts = Arrays.asList(Arrays.asList(5, 7, 11,13), 
                                                     Arrays.asList(1, 3, 5), 
                                                     Arrays.asList(2, 4, 6, 8)); 

// [[5, 7, 11, 13], [1, 3, 5], [2, 4, 6, 8]]
          
List<Integer> listofInts  = listOfListofInts.stream() 
    .flatMap(list -> list.stream()) 
    .collect(Collectors.toList()); 

// [5, 7, 11, 13, 1, 3, 5, 2, 4, 6, 8]
```

[к оглавлению](#Java-8)

### `Match`
Методы `match` проверяют поток на соответствие предикату. Есть такие матчеры :
+ `anyMatch()` - возвращает `true`, если хотя бы один элемент потока соответствует требованиям предиката.
+ `allMatch()` - возвращает `true`, если каждый элемент потока соответствует требованиям предиката.
+ `noneMatch()` - возаращает `true`, если ни один элемент потока не соответствует требованиям предиката.

Сигнатуры методов `anyMatch`, `allMatch`, `noneMatch` в интерфейсе `Stream` : 
```java
boolean anyMatch(Predicate<? super T> predicate);

boolean allMatch(Predicate<? super T> predicate);

boolean noneMatch(Predicate<? super T> predicate);
```

Эти операции являются терминальными, так как они возвращают `boolean`. 

Ниже приведены примеры использования матчеров.
```java
boolean anyStartsWithA = List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
        .stream()
        .anyMatch((s) -> s.startsWith("a"));

System.out.println(anyStartsWithA);      // true

boolean allStartsWithA = List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
        .stream()
        .allMatch((s) -> s.startsWith("a"));

System.out.println(allStartsWithA);      // false

boolean noneStartsWithZ = List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
        .stream()
        .noneMatch((s) -> s.startsWith("z"));

System.out.println(noneStartsWithZ);      // true
```

[к оглавлению](#Java-8)

### `Count`
Метод `count` возвращает точное количество элементов в потоке. Типом возвращаемого значения является long`.

Сигнатура метода `count` в интерфейсе `Stream` : 
```java
long count();
```

Эта операция является терминальной, так как возвращает примитивный тип - `long`.

Ниже приведен пример использования `count`.
```java
long startsWithB = List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
        .stream()
        .filter((s) -> s.startsWith("b"))
        .count();

System.out.println(startsWithB);    // 3
```

[к оглавлению](#Java-8)

### `Reduce`
Метод `reduce` сворачивает элементы потока в один согласно заданной функции. Результатом будет значение того типа, элементы которого лежат в стриме или `Optional`.

Сигнатуры метода `reduce` в интерфейсе `Stream` : 
```java
T reduce(T identity, BinaryOperator<T> accumulator);

Optional<T> reduce(BinaryOperator<T> accumulator);

<U> U reduce(U identity,
             BiFunction<U, ? super T, U> accumulator,
             BinaryOperator<U> combiner);
```

Эта операция является терминальной, так как не возвращает объект потока.

Ниже приведен пример использования `reduce`.
```java
Optional<String> reduced = List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
        .stream()
        .sorted()
        .reduce((s1, s2) -> s1 + "#" + s2);

reduced.ifPresent(System.out::println);
// "aaa1#aaa2#bbb1#bbb2#bbb3#ccc#ddd1#ddd2"
```

[к оглавлению](#Java-8)

### `Collect`
Метод `collect` собирает элементы нашего потока в коллекцию, строку, число и т.д. Для этого он использует параметр типа `Collector`, который как правило берется из одного из статических методов класса `Collectors`. 

Сигнатуры метода `collect` в интерфейсе `Stream` : 
```java
<R, A> R collect(Collector<? super T, A, R> collector);

<R> R collect(Supplier<R> supplier,
              BiConsumer<R, ? super T> accumulator,
              BiConsumer<R, R> combiner);
```

Эта операция является терминальной, так как возвращает сущность, отличную от потока.

Ниже приведен пример использования `collect`.
```java
List<String> = List.of("ddd2", "aaa2", "bbb1", "aaa1", "bbb3", "ccc", "bbb2", "ddd1")
        .stream()
        .sorted()
        .collect(Collectors.toList());
```

[к оглавлению](#Java-8)

#### Parallel Streams
_Параллельные потоки_ - это потоки, операции над которыми выполняются в нескольких потоках процессора. 

При работе с большим объемом данных часто параллельные потоки будут выполнять задачу быстрее последовательного потока.

Например, создадим коллекцию на `1_000_000` уникальных элементов, которую надо отсортировать.
```java
int max = 1000000;
List<String> values = new ArrayList<>(max);
for (int i = 0; i < max; i++) {
    UUID uuid = UUID.randomUUID();
    values.add(uuid.toString());
}
```
Теперь измерим время сортировки в последовательном стриме и параллельном :

Последовательная сортировка :
```java
long t0 = System.nanoTime();

long count = values.stream().sorted().count();
System.out.println(count);

long t1 = System.nanoTime();

long millis = TimeUnit.NANOSECONDS.toMillis(t1 - t0);
System.out.println(String.format("sequential sort took: %d ms", millis));

// sequential sort took: 899 ms
```
Параллельная сортировка :
```java
long t0 = System.nanoTime();

long count = values.parallelStream().sorted().count();
System.out.println(count);

long t1 = System.nanoTime();

long millis = TimeUnit.NANOSECONDS.toMillis(t1 - t0);
System.out.println(String.format("parallel sort took: %d ms", millis));

// parallel sort took: 472 ms
```
Как видим, параллельная сортировка сработала в `2` раза быстрее, при том что куски кода фактически одинаковые.

Но параллельные стримы не всегда являются лучшим вариантом. Например, есть такие кейсы :
+ Размер последовательности маленький, и создание параллельных потоков вместе со всеми служебными операциями может занять большее время, чем если сделать тоже самое в одном последовательном потоке.
+ Не для всех методов стримов подходит параллельное выполнение. Например, метод `reduce` выдает такой результат при вызове его в параллельном стриме :
```java
Stream<String> wordsStream = Stream.of("мама", "мыла", "раму");
String sentence = wordsStream.parallel().reduce("Результат:", (x,y)->x + " " + y);
System.out.println(sentence);       // Результат: мама Результат: мыла Результат: раму
```
Как видим, результат вышел не тот, что ожидался.

[к оглавлению](#Java-8)

#### Метод `Collection.stream()`
Данный дефолтный метод создает поток - объект `ReferencePipeline`, в котором операции будут выполняться последовательно с помощью одного сплитератора.
```java
default Stream<E> stream() {
    return StreamSupport.stream(spliterator(), false);
}
```

[к оглавлению](#Java-8)

#### Метод `Collection.parallelStream()`
Данный дефолтный метод создает поток - объект `ReferencePipeline`, в котором операции будут выполняться параллельно с помощью нескольких сплитераторов.
```java
default Stream<E> parallelStream() {
    return StreamSupport.stream(spliterator(), true);
}
```

[к оглавлению](#Java-8)

## Новые методы `Map`
В Java 8 были добавлены новые методы в интерфейс `Map`, которые позволяют за одну инструкцию делать действия, которые раньше производились с помощью нескольких инструкций.

### `getOrDefault`
`getOrDefault(Object key, V defaultValue) -> V` - поиск значения по ключу, если такой пары нет то возвращается `defaultValue`.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.getOrDefault(42, "not found");  // not found
    ```
  
  [к оглавлению](#Java-8)
  
### `forEach`
`forEach(BiConsumer<? super K, ? super V> action) -> void` - прозводит переданное действие со всеми `Entry` в мапе. Принимает в аргументы `key` и `value` каждой ноды.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.forEach((id, val) -> System.out.println(val));
    ```
  
  [к оглавлению](#Java-8)
  
### `replaceAll`
`replaceAll(BiFunction<? super K, ? super V, ? extends V> function) -> void` - заменяет каждый `Entry` в мапе результатом выполнения переданной функции с `key` и `value` этой ноды в качестве параметров.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map1.replaceAll((key, oldValue) -> oldValue + kay); // val00, val01, val02...
    ```
  
  [к оглавлению](#Java-8)
  
### `putIfAbsent`
`putIfAbsent(K key, V value) -> V` - кладет в мапу пару ключ-значение только, если такого ключа еще нет в ней.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
    ```
  
  [к оглавлению](#Java-8)
  
### `remove`
`remove(Object key, Object value) -> boolean` - удаляет пару ключ-значение из мапы только в том случае, если данному ключу соответствует именно данное значение.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.remove(3, "val3");
    map.get(3);             // val33
    
    map.remove(3, "val33");
    map.get(3);             // null
    ```
  
  [к оглавлению](#Java-8)
  
### `replace`
Этот метод имеет `2` перегрузки :
+ `replace(K key, V oldValue, V newValue) -> boolean` - если `key` в мапе ассоциирован со значением `oldValue`, то заменяет это значение на `newValue`.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.replace(1, "incorrect", "newvalue1");
    map.get(1);            // val1
  
    map.replace(2, "val2", "newvalue2");
    map.get(2);            // newvalue2
    ```
  
  [к оглавлению](#Java-8)
  
+ `replace(K key, V value) -> V` - если по ключу `key` в маппе есть любое значение, тогда заменяет его на значение `value`.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.replace(1, "newvalue");
    map.get(1);            // newvalue
    ```
  
  [к оглавлению](#Java-8)
  
### `computeIfAbsent`
`computeIfAbsent(K key, Function<? super K, ? extends V> mappingFunction) -> V` - если в мапе нет такого ключа или его значение `null`, то вызывается переданная функция с этим ключом-аргументом, и если результат не `null`, то пара ключ-значение кладется в мапу.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.computeIfAbsent(23, num -> "val" + num);
    map.containsKey(23);    // true
    
    map.computeIfAbsent(3, num -> "bam");
    map.get(3);             // val33
    ```
  
  [к оглавлению](#Java-8)
  
### `computeIfPresent`
`computeIfPresent(K key, BiFunction<? super K, ? super V, ? extends V> remappingFunction) -> V` - если в мапе есть такая пара ключ-значение и значение при этом не `null`, вызывается переданная функция с ключом и значнеием в качестве параметров, которая возвращает новое значение для пары. Если результат функции не `null`, то значение по ключу в мапе обновляется. Если посчитанное значение `null`, то пара ключ-значение удаляется из мапы.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.computeIfPresent(3, (num, val) -> val + num);
    map.get(3);             // val33
    
    map.computeIfPresent(9, (num, val) -> null);
    map.containsKey(9);     // false
    ```
  
  [к оглавлению](#Java-8)
  
### `compute`
`compute(K key, BiFunction<? super K, ? super V, ? extends V> remappingFunction) -> V` - в мапе ищется значение по ключу, вне зависимости от возвращенного значения считается результат функции с аргументами ключ и значение, который в свою очередь возвращает новое значение. Если оно не `null`, то новое значение присвается этому ключу в мапе. Если оно все-таки `null`, то если эта пара ключ-значение вообще была в мапе, то удаляется из нее.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.compute(1, (key, value) -> key + value);
    map.get(1);            // val11
    ```
  
  [к оглавлению](#Java-8)
  
### `merge`
`merge(K key, V value, BiFunction<? super V, ? super V, ? extends V> remappingFunction) -> V` - если данного ключа нет в мапе или он ассоциирован со значением `null`, то ему присваивается в пару значение `value`. В другом случае, вызывается переданнная функция со старым значением и значением аргументом в качестве параметров, и возвращаемое значение, если оно не `null`, становится новой парой для ключа. Если же возвращенное значение `null`, то пара ключ-значение удаляется из мапы.
    ```java
    Map<Integer, String> map = new HashMap<>();
    
    for (int i = 0; i < 10; i++) {
        map.putIfAbsent(i, "val" + i);
    }
  
    map.merge(9, "val9", (value, newValue) -> value.concat(newValue));
    map.get(9);             // val9
    
    map.merge(9, "concat", (value, newValue) -> value.concat(newValue));
    map.get(9);             // val9concat
    ```
  
  [к оглавлению](#Java-8)
  
## Оптимизация корзин в `HashMap`
Ранее в `HashMap` корзины из себя всегда представляли односвязные списки, первый элемент которых находился в массиве, лежащем внутри мапы. Из-за этого при худшем раскладе время поиска и удаления элемента могло доходить до __O(N)__(при плохо определенном методе `hashCode()`). 

В Java 8 же была введена оптимизация этих корзин. Заключается она в том, что односвязный список при достижении размера в `8` элементов, при условии что размер массива внутри мапы как минимум `64` ячейки, перестраивается в красно-черное сбалансированное дерево. Это позволяет уменьшить максимальное время поиска и удаления элемента до __O(N log N)__.

Также, при снижении количества элементов в таком дереве до `6`, вне зависимости от размера массива, корзина из дерева перестраивается обратно в односвязный список.

## Новый API для работы со временем и датами
В Java 8 был добавлен новый API для работы с временем и датами, который находится в пакете `java.time`. Далее подробнее про самые важные добавленные классы в этот пакет.

### `Clock` и `Instant`
+ Класс Clock предоставляет доступ к текущей дате и времени. 
+ `Clock` работет с часовыми поясами и может использоваться вместо вызова `System.currentTimeMillis()` для возвращения миллисекунд :
```java
Clock clock = Clock.systemDefaultZone();
long millis = clock.millis();
```
+ Класс `Instant` также представляет точную дату.
+ Объекты класса `Instant` могут быть использованы для создания объектов устаревшего типа `Date` :
```java
Instant instant = clock.instant();
Date legacyDate = Date.from(instant);   // legacy java.util.Date
```

[к оглавлению](#Java-8)

### `ZoneId`
+ Класс `ZoneId` представляет часовые пояса.
+ Доступ к часовым поясам можно получить с помощью статических конструкторов.
+ Часовые пояса содержат смещения, которые важны для конвертации дат и времени в местные :
```java
System.out.println(ZoneId.getAvailableZoneIds());
// prints all available timezone ids

ZoneId zone1 = ZoneId.of("Europe/Berlin");
ZoneId zone2 = ZoneId.of("Brazil/East");
System.out.println(zone1.getRules());
System.out.println(zone2.getRules());

// ZoneRules[currentStandardOffset=+01:00]
// ZoneRules[currentStandardOffset=-03:00]
```

[к оглавлению](#Java-8)

### `LocalTime`
+ Класс `LocalTime` представляет время с учетом часового пояса, к примеру, 12am или 16:25:24.
+ В следующем примере создаются два местных времени для часовых поясов `ZoneId`. Затем оба времени сравниваются, и вычисляется разница между ними в часах и минутах.
```java
ZoneId zone1 = ZoneId.of("Europe/Berlin");
ZoneId zone2 = ZoneId.of("Brazil/East");

LocalTime now1 = LocalTime.now(zone1);
LocalTime now2 = LocalTime.now(zone2);

System.out.println(now1.isBefore(now2));  // false

long hoursBetween = ChronoUnit.HOURS.between(now1, now2);
long minutesBetween = ChronoUnit.MINUTES.between(now1, now2);

System.out.println(hoursBetween);       // -3
System.out.println(minutesBetween);     // -239
```
+ Класс `LocalTime` содержит фабричные методы, которые упрощают создание экземпляров и парсинг строк :
```java
LocalTime late = LocalTime.of(23, 59, 59);
System.out.println(late);       // 23:59:59

DateTimeFormatter germanFormatter =
    DateTimeFormatter
        .ofLocalizedTime(FormatStyle.SHORT)
        .withLocale(Locale.GERMAN);

LocalTime leetTime = LocalTime.parse("13:37", germanFormatter);
System.out.println(leetTime);   // 13:37
```
   
[к оглавлению](#Java-8)

### `LocalDate`
+ Класс `LocalDate` представляет конкретную дату. Например, 29-02-2020.
+ Объекты `LocalDate` - неизменяемы, являются аналогом `LocalTime`, а сам класс `LocalDate` является финальным.
+ Каждая операция в `LocalDate` возвращает новый экземпляр.
+ Пример вычисления новой даты путем сложения или вычитания дней, месяцев или лет :
```java
LocalDate today = LocalDate.now();
LocalDate tomorrow = today.plus(1, ChronoUnit.DAYS);
LocalDate yesterday = tomorrow.minusDays(2);

LocalDate independenceDay = LocalDate.of(2014, Month.JULY, 4);
DayOfWeek dayOfWeek = independenceDay.getDayOfWeek();
System.out.println(dayOfWeek);    // FRIDAY
```
+ Пример парсинга строки в экземпляр `LocalDate` :
```java
DateTimeFormatter germanFormatter = DateTimeFormatter
        .ofLocalizedDate(FormatStyle.MEDIUM)
        .withLocale(Locale.GERMAN);

LocalDate xmas = LocalDate.parse("24.12.2014", germanFormatter);
System.out.println(xmas);   // 2014-12-24
```

[к оглавлению](#Java-8)

### `LocalDateTime`
+ Класс `LocalDateTime` представляет комбинацию времени и даты. 
+ Объекты `LocalDateTime` неизменяемы и работают по аналогии с `LocalTime` и `LocalDate`.
+ Пример использования различных методов для извлечения конкретных значений из даты-времени :
```java
LocalDateTime sylvester = LocalDateTime.of(2014, Month.DECEMBER, 31, 23, 59, 59);

DayOfWeek dayOfWeek = sylvester.getDayOfWeek();
System.out.println(dayOfWeek);      // WEDNESDAY

Month month = sylvester.getMonth();
System.out.println(month);          // DECEMBER

long minuteOfDay = sylvester.getLong(ChronoField.MINUTE_OF_DAY);
System.out.println(minuteOfDay);    // 1439
```
+ Также мы можем получить объект `Instant` путем добавления информации о часовом поясе :
```java
Instant instant = sylvester
        .atZone(ZoneId.systemDefault())
        .toInstant();

Date legacyDate = Date.from(instant);
System.out.println(legacyDate);     // Wed Dec 31 23:59:59 CET 2014
```
+ Форматирование даты-времени происходит так же, как и форматирование даты или времени. Для этого мы можем использовать библиотечные или собственные шаблоны :
```java
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MMM dd, yyyy - HH:mm");

LocalDateTime parsed = LocalDateTime.parse("Nov 03, 2014 - 07:13", formatter);
String string = formatter.format(parsed);
System.out.println(string);     // Nov 03, 2014 - 07:13
```

[к оглавлению](#Java-8)

## Повторяемые аннотации
В Java 8 стало возможным применять одну и ту же аннотацию по отношению к одному и тому же таргету дважды и больше раз благодаря аннотации `@Repeatable`.

Для этого необходимо объявить саму аннотацию как @Repeatable и все так же объявить перент-аннотацию с массивом внутри.
```java
@interface Hints {
    Hint[] value();
}

@Repeatable(Hints.class)
@interface Hint {
    String value();
}
```
Раньше нужно было писать так :
```java
@Hints({
    @Hint("hint1"), 
    @Hint("hint2")
})
class Person {}
```
Теперь же можно записывать и так :
```java
@Hint("hint1")
@Hint("hint2")
class Person {}
```
При использовании нового варианта записи компилятор автоматически подставит перент-аннотацию `@Hints`. Это важно при чтении информации об аннотациях через рефлексию, что можно увидеть в примере ниже.
```java
Hint hint = Person.class.getAnnotation(Hint.class);
System.out.println(hint);                   // null

Hints hints1 = Person.class.getAnnotation(Hints.class);
System.out.println(hints1.value().length);  // 2

Hint[] hints2 = Person.class.getAnnotationsByType(Hint.class);
System.out.println(hints2.length);          // 2
```
Также появились два новых типа элементов, на которых можно использовать аннотации. Это `TYPE_PARAMETER` и `TYPE_USE`.
```java
@Target({ElementType.TYPE_PARAMETER, ElementType.TYPE_USE})
@interface MyAnnotation {}
```

[к оглавлению](#Java-8)
