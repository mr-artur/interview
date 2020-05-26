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
+ [`Predicate.not`](#Predicatenot)
    + [Пример `Predicate.not`](#Пример-Predicatenot)
+ [`Optional.isEmpty`](#OptionalisEmpty)
    + [Пример `Optional.isEmpty`](#Пример-OptionalisEmpty)
+ [`HttpClient` стал частью стандарта Java](#HttpClient-стал-частью-стандарта-Java)
    + [Пример использования `HttpClient`](#Пример-использования-HttpClient)
+ [Новые методы в `java.nio.file.Files`](#Новые-методы-в-javaniofileFiles)
    + [Пример использования `Files.writeString` и `Files.readString`](#Пример-использования-FileswriteString-и-FilesreadString`)

## Что нового появилось в Java 11?
+ Возможность добавления `var` в параметры лямбда-выражений ([_перейти_](#Возможность-добавления-var-в-параметры-лямбда-выражений))
+ Новые методы для `String` : ([_перейти_](#Новые-методы-для-String))
    + `isBlank` ([_перейти_](#isBlank))
    + `lines` ([_перейти_](#lines))
    + `repeat` ([_перейти_](#repeat))
    + `strip` ([_перейти_](#strip))
    + `stripLeading` ([_перейти_](#stripLeading))
    + `stripTrailing` ([_перейти_](#stripTrailing))
+ Добавлен статический метод `not` в `Predicate` ([_перейти_](#Predicatenot))
+ Добавлен метод `isEmpty` в `Optional` и подобные ему классы ([_перейти_](#OptionalisEmpty))
+ `HttpClient` стал частью стандарта Java 11. Теперь Apache HttpClient находится в пакете `java.net.http`. ([_перейти_](#HttpClient-стал-частью-стандарта-Java))
+ Новые методы в `java.nio.file.Files` : ([_перейти_](#Новые-методы-в-javaniofileFiles))
    + `readString` (`2` перегрузки)
    + `writeString` (`2` перегрузки)
+ Новые сборщики мусора _Epsilon Garbage Collector_ и _ZGC_
+ Запуск программ, состоящих из одного файла, одной строкой (просто `java`, без комманды `javac` перед этим)
+ Удаление устаревших методов из `Thread` :
    + удален `destroy()`
    + удален `stop(Throwable)`

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

### `stripTrailing`
Новый метод `stripTrailing` возвращает строку, в которой убраны все невидимые символы в конце строки.

При этом невидимые символы определяются с помощью метода `Character.isWhitespace(char)`.

Сигнатура метода `stripTrailing` в классе `String` :
```java
String stripTrailing();
```

[к оглавлению](#Java-11)

## `Predicate.not`
В Java 11 был добавлен статический метод `not()` в интерфейс `Predicate`.

Этот метод возвращает предикат, который является отрицанием переданного аргумента-предиката.

Сигнатура метода `not` в `Predicate` :
```java
static <T> Predicate<T> not(Predicate<? super T> target);
```

[к оглавлению](#Java-11)

#### Пример `Predicate.not`
```java
jshell> "vasya\n    \npetya".lines().filter(
   ...> Predicate.not(String::isBlank)).collect(
   ...> Collectors.toList());
$12 ==> [vasya, petya]
```
 
[к оглавлению](#Java-11)

## `Optional.isEmpty`
В Java 11 был добавлен метод `isEmpty()` в классы `Optional`, `OptionalInt`, `OptionalLong`, `OptionalDouble`.

Этот метод возвращает `true`, если внутри опционального значения пусто, и `false` в обратном случае.

Сигнатура метода `isEmpty` в `Optional` :
```java
boolean isEmpty();
```

[к оглавлению](#Java-11)

#### Пример `Optional.isEmpty`
```java
var empty = Optional.empty();
empty.isEmpty()     // true

var notEmpty = Optional.of("notEmpty");
empty.isEmpty()     // false
```
 
[к оглавлению](#Java-11)

## `HttpClient` стал частью стандарта Java
До Java 9 Apache `HttpClient` была фактически стандартной библиотекой для отправки HTTP-запросов. В Java 9 `HttpClient` был включён в библиотеки, но только как модуль инкубатора. Начиная с Java 11 `HttpClient` является частью стандартных библиотек. Больше не нужно для этого подключать внешние зависимости. Сам `HttpClient` находится в пакете `java.net.http`.

[к оглавлению](#Java-11)

#### Пример использования `HttpClient`
```java
jshell> import java.net.http.*;
 
jshell> HttpRequest request = HttpRequest.newBuilder().uri(
   ...> java.net.URI.create("https://urvanov.ru")).GET(
   ...> ).build();
request ==> https://urvanov.ru GET
 
jshell> HttpClient client = HttpClient.newHttpClient();
client ==> jdk.internal.net.http.HttpClientImpl@50eac852(1)
 
jshell> HttpResponse<String> response = client.send(request,
   ...>  HttpResponse.BodyHandlers.ofString());
response ==> (GET https://urvanov.ru) 200
 
jshell> response.statusCode();
$25 ==> 200
 
jshell> response.body();
$26 ==> "<!DOCTYPE html>\n<html la...
```

[к оглавлению](#Java-11)

## Новые методы в `java.nio.file.Files`
В Java 11 были добавлены `4` новых метода для класса `Files`. 

Эти методы предназначены для чтения содержимого файла в строки и записи файла из строки :
+ `public static String readString​(Path path) throws IOException`

Читает содержимое файла в строку. Файл расценивается как содержащий текст в кодировке UTF-8.

+ `public static String readString​(Path path, Charset cs) throws IOException`

Читает содержимое файла по пути `path` в строку в указанной кодировке.

+ `public static Path writeString​(Path path, CharSequence csq, OpenOption... options) throws IOException`

Записывает последовательность символов `csq` в файл по пути `path` в кодировке `UTF-8`.

+ `public static Path writeString​(Path path, CharSequence csq, Charset cs, OpenOption... options) throws IOException`

Записывает последовательность символов в файл в уазанной кодировке.

[к оглавлению](#Java-11)

#### Пример использования `Files.writeString` и `Files.readString`
```java
jshell> import java.nio.file.*;
 
jshell> Files.writeString(Paths.get("myfile.txt"), "My string");
$8 ==> myfile.txt
 
jshell> Files.readString(Paths.get("myfile.txt"));
$9 ==> "My string"
```

[к оглавлению](#Java-11)
