# Java 11
+ [Что нового появилось в Java 11?](#Что-нового-появилось-в-Java-11)
+ [Возможность добавления `var` в параметры лямбда-выражений](#Возможность-добавления-var-в-параметры-лямбда-выражений)
+ [Новые методы для `String`](#Новые-методы-для-String)
    + [`isBlank`](#isBlank)
    + [`lines`](#lines)
    + [`repeat`](#repeat)
    + [`strip`](#strip)
    + [`stripLeading`](#stripLeading)
    + [`stripTrailing`](#stripTrailing)

## Что нового появилось в Java 11?
+ Возможность добавления `var` в параметры лямбда-выражений ([_перейти_](#Возможность-добавления-var-в-параметры-лямбда-выражений))
+ Новые методы для `String` : ([_перейти_](#Новые-методы-для-String))
    + `isBlank` ([_перейти_](#isBlank))
    + `lines` ([_перейти_](#lines))
    + `repeat` ([_перейти_](#repeat))
    + `strip` ([_перейти_](#strip))
    + `stripLeading` ([_перейти_](#stripLeading))
    + `stripTrailing` ([_перейти_](#stripTrailing))
+ Добавлен статический метод `not` в `Predicate`
+ Добавлен метод `isEmpty` в `Optional` и подобные ему классы
+ `HttpClient` стал частью стандарта Java 11
+ Новые методы в `java.nio.file.Files` :
    + `readString` (`2` перегрузки)
    + `writeString` (`2` перегрузки)
+ Новые сборщики мусора _Epsilon Garbage Collector_ и _ZGC_
+ Запуск программ, состоящих из одного файла, одной строкой
+ Удаление устаревших методов из `Thread`

[к оглавлению](#Java-11)

## Возможность добавления `var` в параметры лямбда-выражений
В Java 10 был добавлен вывод типа с помощью `var`. Начиная с Java 11 можно использовать `var` и в параметрах лямбда-выражений.

Простой пример :
```java
 list.stream()
     .map((var s) -> s.toLowerCase())
     .collect(Collectors.toList());
```
Но лямбда выражения уже имели и так вывод типа, и данное выражение можно было бы записать и так :
```java
list.stream()
    .map(s -> s.toLowerCase())
    .collect(Collectors.toList());
```
Зачем же нужно было добавлять возможность писать `var` тут? Ответ - для того единственного случая, когда нам необходимо добавить аннотацию к параметру лямбды. Это невозможно сделать без участия какого-либо типа. Чтобы избежать использования явного типа, мы можем использовать `var` для упрощения читаемости, выйдет следующее :
```java
list.stream()
    .map((@Notnull var s) -> s.toLowerCase())
    .collect(Collectors.toList());
```

[к оглавлению](#Java-11)

## Новые методы для `String`
В Java 11 были добавлены `6` новых методов для `String` :
+ `isBlank` - возвращает `true`, если строка пустая или содержит только пробелы, иначе `false`.
+ `lines` - возвращает `Stream` из `String`, которые получаются после разделения строки по строчным разделителям в ней.
+ `repeat` - возвращает строку, значение которой представляет конкатенацию `n` количества повторений этой строки.
+ `strip` - аналог `trim`, но в отличии от него, обрезает не только пробелы в начале и конце строки, но и другие невидимые символы.
+ `stripLeading` - возвращает строку без начальных пробельных (невидимых) символов.
+ `stripTrailing` - возвращает строку без конечных пробельных (невидимых) символов.

[к оглавлению](#Java-11)

### `isBlank`
Новый метод `isBlank` широко используется для проверки объектов `String` на пустоту или что строка состоит только из пробельных символов.

Сигнатура метода `isBlank` в классе `String` :
```java
boolean isBlank();
```

[к оглавлению](#Java-11)

#### Пример `isBlank`
```java
jshell> "      ".isBlank();
$4 ==> true
 
jshell> "".isBlank();
$5 ==> true
 
jshell> " this is not a blank string   ".isBlank();
$6 ==> false
```
 
[к оглавлению](#Java-11)
 
### `lines`
Новый метод `lines` возвращает все строки, разделенные символом перевода строки `\r`, `\n`, или `\r\n` в `Stream`.

Сигнатура метода `lines` в классе `String` :
```java
Stream<String> lines();
```

[к оглавлению](#Java-11)

#### Пример `lines`
```java
jshell> ("Kate goes to the zoo every day.\n"
   ...> + "Catherine likes apples.\r\n"
   ...> + "John is bleeding.\r"
   ...> + "The winter is coming.").lines().forEach(
   ...> System.out::println);
Kate goes to the zoo every day.
Catherine likes apples.
John is bleeding.
```
 
[к оглавлению](#Java-11)

### `repeat`
Новый метод `repeat` возвращает строку, которая содержит исходную строку указанное количество раз.

Сигнатура метода `repeat` в классе `String` :
```java
String repeat(int count);
```

[к оглавлению](#Java-11)

#### Пример `repeat`
```java
jshell> "cat".repeat(3);
$7 ==> "catcatcat"
```
 
[к оглавлению](#Java-11)

### `strip`
Новый метод `strip` возвращает строку, в которой убраны все невидимые символы в начале и конце строки.

При этом невидимые символы определяются с помощью метода `Character.isWhitespace(char)`.

Сигнатура метода `strip` в классе `String` :
```java
String strip();
```

[к оглавлению](#Java-11)

#### Пример `strip`
```java
jshell> "      Hello, Vasya!     ".strip();
$1 ==> "Hello, Vasya!"
```
 
[к оглавлению](#Java-11)

### `stripLeading`
Новый метод `stripLeading` возвращает строку, в которой убраны все невидимые символы в начале строки.

При этом невидимые символы определяются с помощью метода `Character.isWhitespace(char)`.

Сигнатура метода `stripLeading` в классе `String` :
```java
String stripLeading();
```

[к оглавлению](#Java-11)

#### Пример `stripLeading`
```java
jshell> "      Hello, Vasya!     ".stripLeading();
$2 ==> "Hello, Vasya!     "
```
 
[к оглавлению](#Java-11)

### `stripTrailing`
Новый метод `stripTrailing` возвращает строку, в которой убраны все невидимые символы в конце строки.

При этом невидимые символы определяются с помощью метода `Character.isWhitespace(char)`.

Сигнатура метода `stripTrailing` в классе `String` :
```java
String stripTrailing();
```

[к оглавлению](#Java-11)

#### Пример `stripTrailing`
```java
jshell> "      Hello, Vasya!     ".stripTrailing();
$3 ==> "      Hello, Vasya!"
```
 
[к оглавлению](#Java-11)
