## SQL
+ [Что такое _SQL_?](#Что-такое-SQL)
+ [Из чего состоит _SQL_?](#Из-чего-состоит-SQL)
### Операторы
+ [`JOIN` Операторы](#JOIN-Операторы)
    + [Рисунок видов `JOIN` операторов](#Рисунок-видов-JOIN-операторов)
    + [`INNER JOIN`](#INNER-JOIN) ([_синтаксис_](#Синтаксис-оператора-INNER-JOIN)) ([_пример_](#Пример-использования-оператора-INNER-JOIN))
    + [`LEFT JOIN`](#LEFT-JOIN) ([_синтаксис_](#Синтаксис-оператора-LEFT-JOIN)) ([_пример_](#Пример-использования-оператора-LEFT-JOIN))
    + [`RIGHT JOIN`](#RIGHT-JOIN) ([_синтаксис_](#Синтаксис-оператора-RIGHT-JOIN)) ([_пример_](#Пример-использования-оператора-RIGHT-JOIN))
    + [`FULL JOIN`](#FULL-JOIN) ([_синтаксис_](#Синтаксис-оператора-FULL-JOIN)) ([_пример_](#Пример-использования-оператора-FULL-JOIN))
    + [`CROSS JOIN`](#CROSS-JOIN) ([_синтаксис_](#Синтаксис-оператора-CROSS-JOIN)) ([_пример_](#Пример-использования-оператора-CROSS-JOIN))
+ [`CREATE`](#CREATE) ([_синтаксис_](#Синтаксис-оператора-CREATE-TABLE)) ([_пример_](#Пример-использования-оператора-CREATE-TABLE))
+ [`ALTER TABLE`](#ALTER-TABLE) ([_синтаксис_](#Синтаксис-оператора-ALTER-TABLE)) ([_пример_](#Пример-использования-оператора-ALTER-TABLE))
+ [`DROP`](#DROP) ([_синтаксис_](#Синтаксис-оператора-DROP)) ([_пример `DROP TABLE`_](#Пример-использования-оператора-DROP-TABLE)) ([_пример `DROP-DATABASE`_](#Пример-использования-оператора-DROP-DATABASE))
+ [`SELECT`](#SELECT) ([_синтаксис_](#Синтаксис-оператора-SELECT)) ([_примеры_](#Примеры-использования-оператора-SELECT))
+ [`INSERT`](#INSERT) ([_синтаксис_](#Синтаксис-оператора-INSERT)) ([_примеры_](#Примеры-использования-оператора-INSERT))
+ [`UPDATE`](#UPDATE) ([_синтаксис_](#Синтаксис-оператора-UPDATE)) ([_примеры_](#Примеры-использования-оператора-UPDATE))
+ [`DELETE`](#DELETE) ([_синтаксис_](#Синтаксис-оператора-DELETE)) ([_примеры_](#Примеры-использования-оператора-DELETE))
+ [`WHERE`](#WHERE) ([_синтаксис_](#Синтаксис-оператора-WHERE)) ([_примеры_](#Примеры-использования-оператора-WHERE))
+ [`GROUP BY`](#GROUP-BY) ([_синтаксис_](#Синтаксис-оператора-GROUP-BY)) ([_примеры_](#Примеры-использования-оператора-GROUP-BY))
+ [`HAVING`](#HAVING) ([_синтаксис_](#Синтаксис-оператора-HAVING)) ([_примеры_](#Примеры-использования-оператора-HAVING))
+ [`ORDER BY`](#ORDER-BY) ([_синтаксис_](#Синтаксис-оператора-ORDER-BY)) ([_примеры_](#Примеры-использования-оператора-ORDER-BY))
+ [`DISTINCT`](#DISTINCT) ([_синтаксис_](#Синтаксис-оператора-DISTINCT)) ([_примеры_](#Примеры-использования-оператора-DISTINCT))
+ [`AND` и `OR`](#AND) ([_синтаксис `AND`_](#Синтаксис-оператора-AND)) ([_синтаксис `OR`_](#Синтаксис-оператора-OR)) ([_примеры_](#Примеры-использования-операторов-AND-и-OR)) 
+ [`DEFAULT`](#DEFAULT) ([_синтаксис_](#Синтаксис-оператора-DEFAULT)) ([_пример_](#Пример-использования-оператора-DEFAULT)) 
+ [`VIEW`](#VIEW) ([_синтаксис `CREATE VIEW`_](#Синтаксис-оператора-CREATE-VIEW)) ([_пример `CREATE VIEW`_](#Пример-использования-оператора-CREATE-VIEW)) 
+ [`PRIMARY KEY`](#PRIMARY-KEY) ([_синтаксис_](#Синтаксис-оператора-PRIMARY-KEY)) ([_пример_](#Пример-использования-оператора-PRIMARY-KEY)) 
+ [`FOREIGN KEY`](#FOREIGN-KEY) ([_синтаксис_](#Синтаксис-оператора-FOREIGN-KEY)) ([_пример_](#Пример-использования-оператора-FOREIGN-KEY)) 
+ [`UNION`](#UNION) ([_синтаксис_](#Синтаксис-оператора-UNION)) ([_пример_](#Пример-использования-оператора-UNION))  
+ [`LIMIT`](#LIMIT) ([_синтаксис_](#Синтаксис-оператора-LIMIT)) ([_примеры_](#Примеры-использования-оператора-LIMIT))    
+ [`IN`](#IN) ([_синтаксис_](#Синтаксис-оператора-IN)) ([_пример_](#Пример-использования-оператора-IN))     
+ [`TRUNCATE`](#TRUNCATE) ([_синтаксис_](#Синтаксис-оператора-TRUNCATE)) ([_пример_](#Пример-использования-оператора-TRUNCATE)) 
+ [`NOT`](#NOT) ([_синтаксис_](#Синтаксис-оператора-NOT)) ([_примеры_](#Примеры-использования-оператора-NOT)) 
+ [`AS`](#AS) ([_синтаксис_](#Синтаксис-оператора-AS)) ([_пример_](#Пример-использования-оператора-AS)) 
+ [`LIKE`](#LIKE) ([_синтаксис_](#Синтаксис-оператора-LIKE)) ([_примеры_](#Примеры-использования-оператора-LIKE)) 
+ [`BETWEEN`](#BETWEEN) ([_синтаксис_](#Синтаксис-оператора-BETWEEN)) ([_примеры_](#Примеры-использования-оператора-BETWEEN)) 
+ [`GRANT`](#GRANT) ([_синтаксис_](#Синтаксис-оператора-GRANT)) ([_примеры_](#Примеры-использования-оператора-GRANT)) 
+ [`DENY`](#DENY) ([_синтаксис_](#Синтаксис-оператора-DENY)) ([_примеры_](#Примеры-использования-оператора-DENY)) 
+ [`REVOKE`](#REVOKE) ([_синтаксис_](#Синтаксис-оператора-REVOKE)) ([_примеры_](#Примеры-использования-оператора-REVOKE)) 
### Функции
+ [`COUNT`](#COUNT) ([_синтаксис_](#Синтаксис-функции-COUNT)) ([_примеры_](#Примеры-использования-функции-COUNT)) 
+ [`AVG`](#AVG) ([_синтаксис_](#Синтаксис-функции-AVG)) ([_примеры_](#Примеры-использования-функции-AVG)) 
+ [`MIN`](#MIN) ([_синтаксис_](#Синтаксис-функции-MIN)) ([_примеры_](#Примеры-использования-функции-MIN)) 
+ [`MAX`](#MAX) ([_синтаксис_](#Синтаксис-функции-MAX)) ([_примеры_](#Примеры-использования-функции-MAX)) 
+ [`SUM`](#SUM) ([_синтаксис_](#Синтаксис-функции-SUM)) ([_примеры_](#Примеры-использования-функции-SUM)) 
+ [`ROUND`](#ROUND) ([_синтаксис_](#Синтаксис-функции-ROUND)) ([_примеры_](#Примеры-использования-функции-ROUND)) 
+ [`UCASE`](#UCASE) ([_синтаксис_](#Синтаксис-функции-UCASE)) ([_примеры_](#Примеры-использования-функции-UCASE)) 
+ [`LCASE`](#LCASE) ([_синтаксис_](#Синтаксис-функции-LCASE)) ([_примеры_](#Примеры-использования-функции-LCASE)) 
+ [`LEN`](#LEN) ([_синтаксис_](#Синтаксис-функции-LEN)) ([_примеры_](#Примеры-использования-функции-LEN))
+ [`MID`](#MID) ([_синтаксис_](#Синтаксис-функции-MID)) ([_пример_](#Пример-использования-функции-MID))
+ [`NOW`](#NOW) ([_синтаксис_](#Синтаксис-функции-NOW)) ([_пример_](#Пример-использования-функции-NOW))

## Что такое _SQL_?
_SQL_ (Structured Query Language) - это язык структурированных запросов, который используется для управления реляционными базами данных и данными в них.

[к оглавлению](#SQL)

### Из чего состоит _SQL_?
_SQL_ состоит из `4`-х частей :
+ __DDL__ (Data Definition Language) - это работа со структурой БД. В нее входят такие операторы как :
    + `CREATE` (Создание) ([_перейти_](#CREATE))
    + `ALTER` (Изменение) ([_перейти_](#ALTER-TABLE))
    + `DROP` (Удаление) ([_перейти_](#DROP))
+ __DML__ (Data Manipulation Language) - это работа со строками и колонками. В нее входят такие операторы как :
    + `INSERT` ([_перейти_](#INSERT))
    + `SELECT` ([_перейти_](#SELECT))
    + `UPDATE` ([_перейти_](#UPDATE))
    + `DELETE` ([_перейти_](#DELETE))
+ __DCL__ (Data Control Language) - это работа с правами. В нее входят такие операторы как :
    + `GRANT` ([_перейти_](#GRANT))
    + `DENY` ([_перейти_](#DENY))
    + `REVOKE` ([_перейти_](#REVOKE))
+ __TCL__ (Transaction Control Language) - это работа с транзакциями. В нее входят такие операторы как :
    + `BEGIN TRANSACTION`
    + `COMMIT`
    + `ROLLBACK`

[к оглавлению](#SQL)

## `JOIN` Операторы
+ `JOIN` операторы служат для соединения в выборках данных из разных таблиц.
+ Существуют всего `8` видов `JOIN`-ов, `7` являются возможными комбинациями подмножеств пересечения двух множеств + одно получается после перемножения двух множеств.
+ В виде операторов как правило поддерживаются `5` основных `JOIN` - ов :
    + `INNER JOIN` 
    + `LEFT OUTER JOIN`
    + `RIGHT OUTER JOIN`
    + `FULL OUTER JOIN`
    + `CROSS JOIN`
+ Остальные `3` обычно получаются с помощью добавления еще одной строки с `NULL` к запросу :
    + `LEFT EXCLUSIVE JOIN`
    + `RIGHT EXCLUSIVE JOIN`
    + `FULL EXCLUSIVE JOIN`

[к оглавлению](#SQL)

## Рисунок видов `JOIN` операторов
![alt text](https://4.bp.blogspot.com/-O6UyDMbXfEs/WpPb5eWZPEI/AAAAAAAATE8/fbx9wMpktp8APSC0hLkuyfJL9weoia2NACLcBGAs/s1600/LEFT%2Bvs%2BRight%2BOuter%2BJoin%2Bin%2BSQL.png)

[к оглавлению](#SQL)

## `INNER JOIN`
Оператор `INNER JOIN` помогает нам сформировать таблицу из записей двух или нескольких таблиц. Каждая строка из левой таблицы сопоставляется с каждой строкой из правой таблицы, после чего происходит проверка условия. Если условие истинно, то строки попадают в результирующую таблицу. В результирующей таблице строки формируются конкатенацией строк первой и второй таблиц.

+ Главной отличительной чертой `INNER JOIN` является то, что в таблицу-результат попадают ТОЛЬКО те объединенные строки двух таблиц, которые удовлетворяют заданному условию.

[к оглавлению](#SQL)

### Синтаксис оператора `INNER JOIN`
```sql
SELECT column_names [,... n]
FROM Table_1 
INNER JOIN Table_2
ON condition
```
Условие для сравнения задается в операторе `ON`.

[к оглавлению](#SQL)

### Пример использования оператора `INNER JOIN`
Пусть у нас есть две таблицы. Первая из них - `Authors` - содержит информацию об авторах книг.

AuthorID	|AuthorName
|:---:|:---:|
1	|Bruce Eckel
2	|Robert Lafore
3	|Andrew Tanenbaum
4   |Sergei Nemchinskiy

Вторая - `Books` - содержит информацию о написанных книгах.

BookID |AuthorID|	BookName
|:---:|:---:|:---:|
1|3	|Modern Operating System
2|1	|Thinking in Java
3|3	|Computer Architecture
4| NULL	|Programming in Scala

__Задание__. Вывести информацию о написанных авторами книгах. При этом нужно, чтобы выводились только те книги, у которых есть автора, и только те автора, у которых есть книги.
```sql
SELECT Authors.*, Books.BookID, Books.BookName
FROM Authors
INNER JOIN Books
ON Books.AuthorID = Authors.AuthorID
```
Результат :

Authors.AuthorID	|Authors.AuthorName | Authors.BookID | Authors.BookName
|:---:|:---:|:---:|:---:|
3|Andrew Tanenbaum|1 |Modern Operating System
1|Bruce Eckel|2|Thinking in Java
3|Andrew Tanenbaum|3|Programming in Scala

Как видим, в выборку попали только `2` автора и `3` книги, так как с остальными авторами не связаны какие-либо книги, а у оставшейся вне подборки книги в поле `AuthorID` находится `NULL`.

[к оглавлению](#SQL)

## `LEFT JOIN`
Оператор `LEFT JOIN` (он же `LEFT OUTER JOIN`) осуществляет формирование таблицы из записей двух таблиц, и помимо связанных записей, он еще и вставляет в выборку все записи из левой (первой) таблицы, сконкатенированные с `NULL`. В нем, как и в `RIGHT JOIN`, важен порядок следования таблиц, так как от этого будет зависеть результат.

Алгоритм работы `LEFT JOIN` такой :
1. Сначала происходит формирование таблицы с помощью внутреннего соединения `INNER JOIN` левой и правой таблиц, то есть, выбираются только все связанные записи.
2. В результат добавляются записи из левой таблицы, не вошедшие в результат `INNER JOIN`. Для них, соответствующие ячейки, ссылающиеся на значения из правой таблицы, заполняются значениями `NULL`.

[к оглавлению](#SQL)

### Синтаксис оператора `LEFT JOIN`
```sql
SELECT column_names [,... n]
FROM Table_1 
LEFT JOIN Table_2
ON condition
```

[к оглавлению](#SQL)

### Пример использования оператора `LEFT JOIN`
Пусть у нас есть две таблицы. Первая из них - `Authors` - содержит информацию об авторах книг.

AuthorID	|AuthorName
|:---:|:---:|
1	|Bruce Eckel
2	|Robert Lafore
3	|Andrew Tanenbaum
4   |Sergei Nemchinskiy

Вторая - `Books` - содержит информацию о написанных книгах.

BookID |AuthorID|	BookName
|:---:|:---:|:---:|
1|3	|Modern Operating System
2|1	|Thinking in Java
3|3	|Computer Architecture
4| NULL	|Programming in Scala

__Задание__. Вывести информацию о написанных авторами книгах. В результат должны быть видны и автора, не написавшие ни одной книги.
```sql
SELECT Authors.*, Books.BookID, Books.BookName
FROM Authors
LEFT JOIN Books
ON Authors.AuthorID = Books.AuthorID
```
Результат :

Authors.AuthorID	|Authors.AuthorName	|Books.BookID	|Books.BookName
|:---:|:---:|:---:|:---:|
1	|Bruce Eckel	|2	|Thinking in Java
2	|Robert Lafore	|NULL	|NULL
3	|Andrew Tanenbaum	|1	|Modern Operating System
3	|Andrew Tanenbaum	|3	|Computer Architecture
4|Sergei Nemchinskiy|NULL|NULL

Как видим из результата, в выборку были добавлены сконкатенированные связанные записи из обеих таблиц, а также остальные строки из левой таблицы, сконкатенированные с `NULL`.

[к оглавлению](#SQL)

## `RIGHT JOIN`
Оператор `RIGHT JOIN` (он же `RIGHT OUTER JOIN`) осуществляет формирование таблицы из записей двух таблиц, и помимо связанных записей, он еще и вставляет в выборку все записи из правой (второй) таблицы, сконкатенированные с `NULL`. В нем, как и в `LEFT JOIN`, важен порядок следования таблиц, так как от этого будет зависеть результат.

Алгоритм работы `RIGHT JOIN` такой :
1. Сначала происходит формирование таблицы с помощью внутреннего соединения `INNER JOIN` левой и правой таблиц, то есть, выбираются только все связанные записи.
2. В результат добавляются записи из правой таблицы, не вошедшие в результат `INNER JOIN`. Для них, соответствующие ячейки, ссылающиеся на значения из левой таблицы, заполняются значениями `NULL`.

[к оглавлению](#SQL)

### Синтаксис оператора `RIGHT JOIN`
```sql
SELECT column_names [,... n]
FROM Table_1 
RIGHT JOIN Table_2
ON condition
```

[к оглавлению](#SQL)

### Пример использования оператора `RIGHT JOIN`
Пусть у нас есть две таблицы. Первая из них - `Authors` - содержит информацию об авторах книг.

AuthorID	|AuthorName
|:---:|:---:|
1	|Bruce Eckel
2	|Robert Lafore
3	|Andrew Tanenbaum
4   |Sergei Nemchinskiy

Вторая - `Books` - содержит информацию о написанных книгах.

BookID |AuthorID|	BookName
|:---:|:---:|:---:|
1|3	|Modern Operating System
2|1	|Thinking in Java
3|3	|Computer Architecture
4| NULL	|Programming in Scala

__Задание__. Вывести информацию о написанных авторами книгах. В результат должны войти и книги без авторов.
```sql
SELECT Authors.*, Books.BookID, Books.BookName
FROM Authors
RIGHT JOIN Books
ON Authors.AuthorID = Books.AuthorID
```
Результат :

Authors.AuthorID	|Authors.AuthorName|	Books.BookID	|Books.BookName
|:---:|:---:|:---:|:---:|
3|	Andrew Tanenbaum|	1	|Modern Operating System
1	|Bruce Eckel	|2	|Thinking in Java
3|	Andrew Tanenbaum	|3	|Computer Architecture
NULL|	NULL|	4	|Programming in Scala

Как видим из результата, `RIGHT JOIN` помог нам достать все связанные записи таблиц, а также остальные записи правой таблицы, сконкатенированные со значениями `NULL`.

[к оглавлению](#SQL)

## `FULL JOIN`
Оператор `FULL JOIN` (он же `FULL OUTER JOIN`) осуществляет формирование таблицы из записей двух таблиц, и помимо связанных записей, он также добавляет как остальные записи левой таблицы, сконкатенированные с `NULL`, так и остальные записи правой таблицы, сконкатенированные с `NULL`.

Оператор `FULL JOIN` является симметричным, а поэтому порядок таблиц для его результата не важен.

Действие оператора `FULL JOIN` можно воспринимать как `INNER JOIN` + `LEFT JOIN` + `RIGHT JOIN`, с исключенными повторяющимися выборками связанных записей.

Алгоритм работы оператора `FULL JOIN` :
1. Формирование результирующей таблицы из связанных записей двух таблиц с помощью `INNER JOIN`.
2. Добавление в результирующую таблицу остальных значений из левой таблицы, сконкатенированных с `NULL`.
3. Добавление в результирующую таблицу остальных значений из правой таблицы, сконкатенированных с `NULL`.

[к оглавлению](#SQL)

### Синтаксис оператора `FULL JOIN`
```sql
SELECT column_names [,... n]
FROM Table_1 
FULL JOIN Table_2
ON condition
```

[к оглавлению](#SQL)

### Пример использования оператора `FULL JOIN`
Пусть у нас есть две таблицы. Первая из них - `Authors` - содержит информацию об авторах книг.

AuthorID	|AuthorName
|:---:|:---:|
1	|Bruce Eckel
2	|Robert Lafore
3	|Andrew Tanenbaum
4   |Sergei Nemchinskiy

Вторая - `Books` - содержит информацию о написанных книгах.

BookID |AuthorID|	BookName
|:---:|:---:|:---:|
1|3	|Modern Operating System
2|1	|Thinking in Java
3|3	|Computer Architecture
4| NULL	|Programming in Scala

__Задание__. Вывести информацию о написанных авторами книгах. При этом вывести также книги без авторов и авторов без книг.
```sql
SELECT Authors.*, Books.BookID, Books.BookName
FROM Authors
FULL JOIN Books
ON Authors.AuthorID = Books.AuthorID
```
Результат :

Authors.AuthorID	|Authors.AuthorName	|Books.BookID	|Books.BookName
|:---:|:---:|:---:|:---:|
1	|Bruce Eckel|	2	|Thinking in Java
2	|Robert Lafore|	NULL	|NULL
3	|Andrew Tanenbaum	|1|	Modern Operating System
3	|Andrew Tanenbaum	|3|	Computer Architecture
4|Sergei Nemchinskiy|NULL|NULL
NULL	|NULL	|4	|Programming in Scala

Как видим, `FULL JOIN` нам помог вывести связанные строки из обеих таблиц, а также остальные строки левой таблицы, сконкатенированные с `NULL`, и остальные строки правой таблицы, сконкатенированные с `NULL`.

[к оглавлению](#SQL)

## `CROSS JOIN`
Оператор `CROSS JOIN` формирует таблицу с помощью перемножения множеств записей из двух таблиц. 

При использовании оператора `CROSS JOIN` каждая строка левой таблицы конкатенируется с каждой строкой из правой таблицы. В результате получается таблица со всеми возможными сочетаниями строк из обеих таблиц.

Оператор `CROSS JOIN` формирует таблицу перекрестным соединением (декартовым произведением) двух таблиц.

[к оглавлению](#SQL)

### Синтаксис оператора `CROSS JOIN`
```sql
SELECT column_names [,... n]
FROM Table_1 
CROSS JOIN Table_2
```
Следует обратить внимание, что в операторе отсутствует условие `ON`, так как оно тут не надо.

[к оглавлению](#SQL)

### Пример использования оператора `CROSS JOIN`
Пусть у нас есть две таблицы. Первая из них - `Authors` - содержит информацию об авторах книг.

AuthorID	|AuthorName
|:---:|:---:|
1	|Bruce Eckel
2	|Robert Lafore
3	|Andrew Tanenbaum

Вторая - `Books` - содержит информацию о написанных книгах.

BookID |AuthorID|	BookName
|:---:|:---:|:---:|
1|3	|Modern Operating System
2|1	|Thinking in Java
3|3	|Computer Architecture

__Задание__. Вывести декартово произведение обеих таблиц.
```sql
SELECT Authors.*, Books.BookID, Books.BookName
FROM Authors
CROSS JOIN Books
```
Также аналогичный результат даст такая запись (тут произойдет неявный `CROSS JOIN`) :
```sql
SELECT Authors.*, Books.BookID, Books.BookName
FROM Authors, Books
```
Результат :

Authors.AuthorID	|Authors.AuthorName	|Books.BookID	|Books.BookName
|:---:|:---:|:---:|:---:|
1	|Bruce Eckel	|1	|Modern Operating System
1	|Bruce Eckel	|2	|Thinking in Java
1	|Bruce Eckel	|3|	Computer Architecture
2	|Robert Lafore|1	|Modern Operating System
2	|Robert Lafore	|2|	Thinking in Java
2	|Robert Lafore	|3	|Computer Architecture
3	|Andrew Tanenbaum	|1|	Modern Operating System
3	|Andrew Tanenbaum	|2	|Thinking in Java
3	|Andrew Tanenbaum	|3	|Computer Architecture

В результате, как мы видим, в таблице получилось `3 x 3 = 9` строк, то есть каждая строка из левой таблицы была сконкатенирована с каждой строкой из правой.

[к оглавлению](#SQL)

## `CREATE`
Оператор `CREATE` служит для создания объектов базы данных либо самой БД (`CREATE DATABASE`).   

Под объектами базы данных, которые можно создать с помощью оператора `CREATE`, подразумеваются таблицы (`CREATE TABLE`) и представления (`CREATE VIEW`).

[к оглавлению](#SQL)

#### Синтаксис оператора `CREATE TABLE`
Синтаксис оператора `CREATE` выглядит следующим образом :
```sql
CREATE TABLE table_name (
    column_name1 data_type(size),
    column_name2 data_type(size),
    column_name3 data_type(size)
    ...
)
```

[к оглавлению](#SQL)

#### Пример использования оператора `CREATE TABLE`
Пример использования оператора `CREATE TABLE` :
```sql
CREATE TABLE Planets (
    ID int,
    PlanetName varchar(10),
    Radius float (10),
    SunSeason float(10),
    OpeningYear int,
    HavingRings bit,
    Opener varchar(30)
)
```
После выполнения этого _SQL_ кода будет создана таблица с соответствующими полями.

[к оглавлению](#SQL)

## `ALTER TABLE`
Оператор `ALTER TABLE` используется для внесения изменений в структуру уже существующей таблицы.

[к оглавлению](#SQL)

#### Синтаксис оператора `ALTER TABLE`
Синтаксис оператора `ALTER TABLE` выглядит следующим образом :
```sql
ALTER TABLE table_name
ADD column_name datatype
```

[к оглавлению](#SQL)

#### Пример использования оператора `ALTER TABLE`
Имеется следующая таблица `Artists` :

|Singer	        |Album	  |Year	     |Sale   |
|:-------------:|:-------:|:--------:|:-----:|
|The Prodigy	| Invaders Must Die |	2008	| 1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

Добавим столбец `Producer`, используя оператор `ALTER TABLE` :
```sql
ALTER TABLE Artists
ADD Producer varchar(20)
```
В результате в таблицу будет добавлен пустой столбец `Producer` :
```sql
SELECT * FROM Artists
```

|Singer	        |Album	  |Year	     |Sale   | Producer |
|:-------------:|:-------:|:--------:|:-----:|:---------|
|The Prodigy	| Invaders Must Die |	2008	| 1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

[к оглавлению](#SQL)

## `DROP`
Оператор `DROP` является универсальным оператором удаления объектов базы данных, или самой БД (`DROP DATABASE`).

[к оглавлению](#SQL)

#### Синтаксис оператора `DROP`
Оператор `DROP` имеет одинаковый синтаксис для удаления разных объектов :
```sql
DROP [ INDEX | TABLE | DATABASE ] object
```

[к оглавлению](#SQL)

#### Пример использования оператора `DROP TABLE`
Удалим таблицу `Artists` :
```sql
DROP TABLE Artists;
```

[к оглавлению](#SQL)

#### Пример использования оператора `DROP DATABASE`
Удалим базу данных `Library` :
```sql
DROP DATABASE Library;
```

[к оглавлению](#SQL)

## `SELECT`
Оператор `SELECT` помогает производить выборку значений, находящихся в базе данных. Он является одним из основных операторов _SQL_.

В структуру запроса с использованием оператора `SELECT` могут быть включены многие вспомогательные операторы, которые могут например уточнять условие выбора, группировать элементы или сортировать их.

[к оглавлению](#SQL)

#### Синтаксис оператора `SELECT`
```sql
SELECT column_list
FROM table_name
[WHERE сondition
GROUP BY expression
HAVING condition
ORDER BY expression]
```
Тут необязательные операторы окружены скобками `[` и `]`. Таким образом, обязательными являются только `SELECT` и `FROM`.

В параметре `column_list` указываются названия столбцов таблицы, которые необходимо вывести, либо символ `*`, который сообщает о том, что нужно вывести все столбцы таблицы. Ключевым словом `FROM` задается название одной или нескольких таблиц, из которых нужно брать столбцы. Оператор `WHERE` задает дополнительные условия выборки. Оператор `GROUP BY` используется для группировки результирующих строк по одному или нескольким столбцам. Оператор `HAVING` включается в запрос для задания условия агрегатных функций. И последний оператор `GROUP BY` используется для сортировки выбранных строк. 

[к оглавлению](#SQL)

#### Примеры использования оператора `SELECT`

Предположим, у нас есть таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener |
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88 |1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 1__. Необходимо вывести названия всех планет (`PlanetName`).
```sql
SELECT PlanetName FROM Planets
```
Результат :

|PlanetName|
|:-------:|
|Mars|
|Saturn|
|Neptune|
|Mercury|
|Venus|

__Пример 2__. Необходимо вывести названия всех планет, у которых есть кольца (`HavingRings`).
```sql
SELECT PlanetName FROM Planets WHERE HavingRings = 'Yes'
```
Результат :

|PlanetName|
|:---:|
|Saturn|
|Neptune|

__Пример 3__. Необходимо вывести информацию о планете Нептун :
```sql
SELECT * FROM Planets WHERE PlanetName = 'Neptune'
```
Результат :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|

[к оглавлению](#SQL)

## `INSERT`
Оператор `INSERT` позволяет добавлять новые записи (строки) в таблицы.

[к оглавлению](#SQL)

#### Синтаксис оператора `INSERT`

Оператор `INSERT` имеет следующий синтаксис :
```sql
INSERT INTO table_name ([column_name, ... ]) VALUES (expressions, ...)
```
Также значения могут быть записаны и без указания столбцов :
```sql
INSERT INTO table_name VALUES (expressions, ...)
```
Также запись значений может производиться с помощью оператора `SELECT` :
```sql
INSERT INTO table_name SELECT column_name,... FROM table_name
```
Используя оператор `SELECT`, можно вставить более одной записи. В случае, если для значения каких-то столбцов не переданы, они будут заменены на значение по умолчанию `null`.

[к оглавлению](#SQL)

#### Примеры использования оператора `INSERT`
__Пример 1__. Предположим, что имеется следующая таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:----:|:---:|:---:|:---:|:---:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|

__Задание__. Необходимо добавить новую запись в таблицу со следующими значениями : 
+ ID : 4
+ PlanetName : Venus
+ Radius : 6051;
+ SunSeason : 243
+ OpeningYear : 1610
+ HavingRings : No
+ Opener : Galileo Galilei
```sql
INSERT INTO Planets (ID, PlanetName, Radius, SunSeason, OpeningYear, HavingRings, Opener)
VALUES (4, "Venus", 6051, 243, 160, "No", "Galileo Galilei")
```
Теперь выведем снова всю таблицу : 
```sql
SELECT * FROM Planets
```
Получим :

| ID	| PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:-----:|:---:|:---:|:----:|:----:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

Как видим, в таблицу была добавлена новая запись.

__Пример 2__. Предположим, что имеются две таблицы - одна для планет без колец, вторая для планет с кольцами. Называются они соответственно `PlanetsWithoutRings` и `PlanetsWithRings`. Отличаться они будут значением поля `HavingRings`. В первой таблице все значения в этом столбце будут `No`, во второй - `Yes`.

`PlanetsWithoutRings` :

| ID	| PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:-----:|:---:|:---:|:----:|:----:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No|	Christiaan Huygens|
|2	|Mercury	|2439	|115.88	|1631	|No	|Nicolaus Copernicus|
|3	|Venus|	6051	|243	|1610	|No	|Galileo Galilei|

`PlanetsWithRings` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:-----:|:---:|:---:|:----:|:----:|:---:|:---:|
|1	|Saturn	|60268|	10759.22|	—	|Yes	|—|
|2	|Neptune	|24764	|60190|	1846	|Yes	|John Couch Adams|

__Задание__. Необходимо вставить записи из таблицы `PlanetsWithRings` в таблицу `PlanetsWithoutRings`.

Данную задачу можно было бы решить двумя запросами, второй был бы как в примере 1, но тут мы воспользуемся вставкой строк с помощью оператора `SELECT`.
```sql
INSERT INTO PlanetsWithoutRings
SELECT ID, PlanetName, Radius, SunSeason, OpeningYear, HavingRings, Opener
FROM PlanetsWithRings
```
Так как названия столбцов в таблицах совпадают, то указывать их необязательно. Вышеуказанный запрос возьмет все значения из указанных столбцов из одной таблицы и вставит их в другую. С помощью следующего запроса посморим, какой стала теперь результирующая таблица :
```sql
SELECT * FROM PlanetsWithoutRings
```
Получим :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:-----:|:---:|:---:|:----:|:----:|:---:|:---:|
|1|	Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|2	|Mercury	|2439	|115.88	|1631	|No	|Nicolaus Copernicus|
|3	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|
|1	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|2	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|

Как видим, все значения из таблицы `PlanetsWithRings` вставились в таблицу `PlanetsWithoutRings`.

[к оглавлению](#SQL)

## `UPDATE`
Оператор `UPDATE` используется для изменения значений в записях таблицы.

[к оглавлению](#SQL)

#### Синтаксис оператора `UPDATE`

Оператор `UPDATE` имеет следующий синтаксис :
```sql
UPDATE table_name 
SET expression 
[WHERE condition]
```
Оператор `WHERE` тут является не обязательным, но без него обновляться значения указанных столбцов во всех записях таблицы.

После ключевого слова `SET` идет список столбцов таблицы, которые необходимо изменить, и новые значения в формате `Имя_столбца = значение`.

Дополнительное условие, описываемое в операторе `WHERE`, помогает более гибко манипулировать данными.

[к оглавлению](#SQL)

#### Примеры использования оператора `UPDATE`
Имеется следующая таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener
|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|2	|Saturn|	60268	|10759.22|	—	|Yes	|—|
|3	|Neptune	|24764|	60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88	|1631	|No|	Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No|	Galileo Galilei|

__Пример 1__. Необходимо изменить название планеты с ID = 3 на Плутон.
```sql
UPDATE Planets
SET PlanetName = 'Pluton'
WHERE ID = 3
```
В этом примере оператор `WHERE` является обязательным, так как без него бы имена всех планет в таблице изменились бы на Плутон. В данном случае мы использовали нахождение записи по ID, которое является первичным ключом и помогает нам идентифицировать запись.

Выполним запрос `SELECT`, чтобы посмотреть изменения в записи :
```sql
SELECT * FROM Planets
WHERE ID = 3
```
Получим :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
|3	|Pluton	|24764	|60190	|1846	|Yes	|John Couch Adams|

Как видим, у записи новое имя планеты.

__Пример 2__. У первых `3` - х записей в таблице изменить значение наличия колец (`HavingRings`) на `No` и и обнулить поле `ID`. 

Запрос для MySQL :
```sql
UPDATE Planets
SET HavingRings = 'No', ID = NULL
LIMIT 3
```

Запрос для MS SQL Server :
```sql
UPDATE TOP(3) Planets
SET HavingRings = 'No', ID = NULL
```

Теперь выполним проверку :

Запрос для MySQL : 
```sql
SELECT * FROM Planets
LIMIT 3
```

Запрос для MS SQL Server : 
```sql
SELECT TOP(3) * FROM Planets
```
Получим :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
|NULL	|Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|NULL	|Saturn	|60268	|10759.22	|—	|No	|—|
|NULL	|Neptune	|24764	|60190	|1846	|No	|John Couch Adams

Как видим, `ID` у записей успешно обнулились, а также значения `HavingRings` у них стали `No`.

[к оглавлению](#SQL)

## `DELETE`
Оператор `DELETE` служит для удаления строк из таблицы или представления.

[к оглавлению](#SQL)

#### Синтаксис оператора `DELETE`

Оператор `DELETE` имеет следующий синтаксис :
```sql
DELETE FROM table_name 
[WHERE condition];
```
Если условие `WHERE` отсутствует, то удалятся все строки из таблицы или представления (представление должно быть обновляемым).

[к оглавлению](#SQL)

#### Примеры использования оператора `DELETE`
Имеется следующая таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener
|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|2	|Saturn|	60268	|10759.22|	—	|Yes	|—|
|3	|Neptune	|24764|	60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88	|1631	|No|	Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No|	Galileo Galilei|

__Пример 1__. Необходимо удалить все записи из таблицы `Planets`.
```sql
DELETE FROM Planets
```

__Пример 2__. Необходимо удалить записи из таблицы `Planets`, которые не имеют колец.
```sql
DELETE FROM Planets
WHERE HavingRings = 'No'
```

__Пример 3__. Необходимо удалить запись из таблицы `Planets` с ID = 3.
```sql
DELETE FROM Planets
WHERE ID = 3
```

[к оглавлению](#SQL)

## `WHERE`
Оператор `WHERE` служит для задания условий выборки, вставки, обновления и удаления записей. 

[к оглавлению](#SQL)

#### Синтаксис оператора `WHERE`
Оператор `WHERE` имеет следующий синтаксис :
```sql
WHERE condition
```
Условие `condition` может в себя включать предикаты `ANR`, `OR`, `NOT`, `LIKE`, `BETWEEN`, `IS`, `IN`, ключевое слово `NULL`, а также операторы сравнения и равенства (например, `<`, `>`, `=`, `<>`).

[к оглавлению](#SQL)

#### Примеры использования оператора `WHERE`
Имеется следующая таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88|	1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 1__. Вывести все записи, значение радиуса (`Radius`) которых находится в пределах от `3000` до `9000`.
```sql
SELECT * FROM Planets
WHERE Radius BETWEEN 3000 AND 9000
```
Или методом глубой силы :
```sql
SELECT * FROM Planets
WHERE Radius >= 3000 AND Radius <= 9000
```
Получим :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:---:|:---:|:---:|:----:|:---:|:---:|:---:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 2__. Вывести название планеты (`PlanetName`), год ее открытия (`OpeningYear`), имя первооткрывателя (`Opener`) планет, чье название не начинается и заканчивается на букву `s`.
```sql
SELECT PlanetName, OpeningYear, Opener 
FROM Planets
WHERE PlanetName NOT LIKE 's%'
AND PlanetName NOT LIKE 'S%'
```
Получим :

|PlanetName	|OpeningYear	|Opener|
|:---:|:---:|:---:|
|Neptune	|1846	|John Couch Adams|
|Mercury	|1631	|Nicolaus Copernicus|

[к оглавлению](#SQL)

## `GROUP BY`
Оператор `GROUP BY` используется для объединения строк выборки по одному или нескольким столбцам.

[к оглавлению](#SQL)

#### Синтаксис оператора `GROUP BY`
Оператор `GROUP BY` имеет следующий синтаксис :
```sql
GROUP BY column_name
```
С использованием оператора `GROUP BY` тесно связано использование агрегатных функций и оператора `HAVING`.

[к оглавлению](#SQL)

#### Примеры использования оператора `GROUP BY`
Предположим, что имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Пример 1__. Найти сумму продаж альбомов `Sale` всех исполнителей (`Singer`).
```sql
SELECT Singer, SUM(Sale) AS AllSales
FROM Artists
GROUP BY Singer
```
Результат :

|Singer	|AllSales|
|:---:|:---:|
|Drowning Pool	|1700000|
|Massive Attack	|5400000|
|The Prodigy	|3300000|

В данном запросе используется оператор `AS`, позволяющий создать новое имя столбца `AllSales` на выходе. В данном случае это необязательно, а сделано для большей информативности.

__Пример 2__. Узнать в каком году был выпущен последний альбом каждой из групп.
```sql
SELECT Singer, MAX(Year) AS LatestAlbumYear
FROM Artists
GROUP BY Singer
```
Результат :

|Singer	|LastAlbumYear|
|:---:|:---:|
|Drowning Pool	|2013|
|Massive Attack	|2004|
|The Prodigy	|2008|

[к оглавлению](#SQL)

## `HAVING`
Оператор `HAVING` является указателем на результат выполнения агрегатных функций. Агрегатная функция - это функция, возвращающая какое-то одно значение по набору значений столбца. Такими функциями являются `COUNT()`, `MIN()`, `MAX()`, `AVG()`, `SUM()`.

Оператор `HAVING` аналогичен оператору `WHERE`, за исключением того, что применяется не для всего набора значений таблицы, а для набора созданного оператором `GROUP BY` и применяется строго после него.

[к оглавлению](#SQL)

#### Синтаксис оператора `HAVING`
Оператор `HAVING` имеет следующий синтаксис :
```sql
HAVING aggregate_function(column_name) operator value
```

[к оглавлению](#SQL)

#### Примеры использования оператора `HAVING`
Имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Пример 1__. Вывести название исполнителей (`Singer`), число продаж альбомов (`Sale`) которого больше `2000000`.
```sql
SELECT Singer, SUM(SALE)
FROM Artists
GROUP BY Singer
HAVING SUM(SALE) > 2000000
```
Результат :

|Singer	|Sum(Sale)|
|:---:|:---:|
|Massive Attack	|54000000|
|The Prodigy	|33000000|

В результат не попала группа `Drowning Pool` из-за того, что число продаж их альбомов равно `1700000`.

__Пример 2__. Вывести названия исполнителей, которые исполнялись еще до 1995 года.
```sql
SELECT Singer, MIN(Year)
FROM Artists
GROUP BY Singer
HAVING MIN(YEAR) < 1995
```
Результат :

|Singer	|MIN(Year)|
|:---:|:---:|
|The Prodigy	|1994|

[к оглавлению](#SQL)

## `ORDER BY`
Оператор `ORDER BY` выполняет сортировку выходных строк. Этот оператор можно применять как к числовым столбцам, так и к строковым. В последнем случае, сортировка будет происходить по алфавиту.

[к оглавлению](#SQL)

#### Синтаксис оператора `ORDER BY`
Оператор `ORDER BY` имеет следующий синтаксис :
```sql
ORDER BY column_name [ASC | DESC]
```
Сортировка может происходить как по возрастанию, так и по убыванию значений :
+ Параметр `ASC` (по умолчанию) устанавливает порядок сортировки по возрастанию, от меньших значений к большим.
+ Параметр `DESC` устанавливает порядок сортировки по убыванию, от больших значений к меньшим.

[к оглавлению](#SQL)

#### Примеры использования оператора `ORDER BY`
Имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Пример 1__. Вывести все записи таблицы, упорядоченные по названию исполнителя.
```sql
SELECT *
FROM Artists
ORDER BY Singer
```
Результат :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|Drowning Pool	|Sinner	|2001	|400000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Drowning Pool	|Resilience	|2013	|500000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|Massive Attack	|100th Window	|2003	|1200000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|

__Пример 2__. Вывести названия исполнителя, альбома, год выпуска тех альбомов, которые выпущены после 2005 года, упорядоченные по убыванию года.
```sql
SELECT Singer, Album, Year
FROM Artists
WHERE Year > 2005
ORDER BY Year DESC
```
Результат :

Singer	|Album	|Year
|:---:|:---:|:---:|
Drowning Pool	|Resilience	|2013
The Prodigy|	Invaders Must Die	|2008
Drowning Pool	|Full Circle	|2007

[к оглавлению](#SQL)

## `DISTINCT`
Оператор `DISTINCT` используется для того, чтобы указать, что мы работаем только с уникальными значениями столбца.

Оператор `DISTINCT` нашел широкое применение в операторе `SELECT` для выборки уникальных значений. Так же он используется в агрегатных функциях.

[к оглавлению](#SQL)

#### Синтаксис оператора `DISTINCT`
Оператор `DISTINCT` имеет следующий синтаксис :
```sql
SELECT DISTINCT column_name FROM table_name
```

[к оглавлению](#SQL)

#### Примеры использования оператора `ORDER BY`
Имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Пример 1__. Вывести, какие исполнители имеются в таблице.
```sql
SELECT DISTINCT Singer
FROM Artists
```
Результат :

|Singer|
|:---:|
|The Prodigy|
|Drowning Pool|
|Massive Attack|

__Пример 2__. Вывести количество уникальных исполнителей в таблице.
```sql
SELECT COUNT(DISTINCT Singer) 
AS SingersCount 
FROM Artists
```
Результат :

SingersCount|
|:---:|
3|

[к оглавлению](#SQL)

## `AND` и `OR`
Операторы `AND` и `OR` - это предикаты языка SQL, служащие для построения логических выражений.

В SQL предикатами называются операторы, возвращающие значения `TRUE` или `FALSE`.

Предикат `AND` - эквивалент логичного умножения (конъюнкции).

Предикат `OR` - эквивалент логического сложения (дизъюнкции).

Таблица истинности для этих предикатов :

first_expression	|last_expression	|AND	|OR
|:----:|:---:|:---:|:---:|
TRUE	|TRUE|	TRUE|	TRUE
TRUE	|FALSE|	FALSE|	TRUE
FALSE	|TRUE|	FALSE|	TRUE
FALSE	|FALSE|	FALSE|  	FALSE

Из таблицы видно, что для выполнения условия предиката `AND` должны выполняться оба условия, а для выполнения условия предиката `OR` должно выполняться хотя бы одно условие.

[к оглавлению](#SQL)

#### Синтаксис оператора `AND`
```sql
boolean_expression AND boolean_expression
```

[к оглавлению](#SQL)

#### Синтаксис оператора `OR`
```sql
boolean_expression OR boolean_expression
```

[к оглавлению](#SQL)

#### Примеры использования операторов `AND` и `OR`
Предположим, что имеется таблица `Planets` :

ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1|	Mars	|3396	|687	|1659	|No	|Christian Huygens
2	|Saturn	|60268	|10759.22	|—	|Yes	|—
3|	Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams
4|	Mercury	|2439	|115.88	|1631	|No	|Nicolaus Copernicus
5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei

__Пример 1__. Вывести записи планет, у которых радиус планеты меньше `10000` и открытых (`OpeningYear`) после `1620`.
```sql
SELECT * 
FROM Planets
WHERE Radius < 10000 AND OpeningYear > 1620
```
ID	|PlanetName|	Radius	|SunSeason	|OpeningYear	|HavingRings|	Opener
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Mars	|3396	|687	|1659	|No	|Christian Huygens
4	|Mercury|	2439|	115.88	|1631	|No|	Nicolaus Copernicus

__Пример 2__. Вывести записи планет, названия которых начинаются с буквы `N` или заканчиваются на букву `s` и не имеющие колец.
```sql
SELECT *
FROM Planets
WHERE (PlanetName LIKE 'N%' OR PlanetName LIKE '%s') AND HavingRings = 'No'
```
Результат :

ID	|PlanetName|	Radius|	SunSeason|	OpeningYear	|HavingRings	|Opener
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Mars	|3396	|687	|1659	|No|	Christian Huygens
5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei

В этом примере используется как предикат `AND`, так и предикат `OR`. В запросах их можно использовать сколько угодно раз (так же как и ограничивающие их скобки) для задания более точного условия выборки.

[к оглавлению](#SQL)

## `DEFAULT`
Оператор `DEFAULT` определяет, каким значением будет заполняться тот или иной столбец по умолчанию. Указывается при создании таблицы. Данное значение будет вставлять в запись, если иное не указано при `INSERT`.
 
 [к оглавлению](#SQL)
 
#### Синтаксис оператора `DEFAULT`
```sql
CREATE TABLE table_name (
    column_name1 data_type(size) DEFAULT 'default_name'
)
```

[к оглавлению](#SQL)

#### Пример использования оператора `DEFAULT`
__Задание__. Создать таблицу `Planets`, где по умолчанию в столбце `HavingRings` будет стоять значение `No`.

```sql
CREATE TABLE Planets (
    ID int,
    PlanetName varchar(10),
    Radius float (10),
    SunSeason float(10),
    OpeningYear int,
    HavingRings bit DEFAULT 'No',
    Opener varchar(30)
)
```
Теперь при заполнении таблицы оператором `INSERT`, если мы не станем указывать значения поля `HavingRings`, в него будет автоматически подставлено значение `No`.

[к оглавлению](#SQL)

## `VIEW`
`View` - это объект базы данных, который является представлением. Представление - это виртуальная таблица, внутреннее содержимое которой определяется исходя из параметров запроса. 

Представления широко используются в двух случаях :
+ Когда надо представить информацию из базы данных в удобном для чтения виде.
+ Из соображений безопасности - предоставляя возможность пользователям обращаться к данным, но при этом не давая им доступ к исходным таблицам.

[к оглавлению](#SQL)

#### Синтаксис оператора `CREATE VIEW`
Для создания представления используется оператор `CREATE` и синтаксис выглядит следующим образом :
```sql
CREATE VIEW view_name
AS SELECT column_name
FROM table_name
WHERE condition
```

[к оглавлению](#SQL)

#### Пример использования оператора `CREATE VIEW`
Имеется следующая таблица `Planets` :

ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1|	Mars	|3396	|687	|1659	|No	|Christian Huygens
2	|Saturn	|60268	|10759.22	|—	|Yes	|—
3|	Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams
4|	Mercury	|2439	|115.88	|1631	|No	|Nicolaus Copernicus
5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei

__Задание__. Создать на основе таблицы `Planets` представление, содержащее в себе название планеты и год ее открытия.
```sql
CREATE VIEW PlanetsView
AS SELECT PlanetName, OpeningYear
FROM Planets
```
В результате этого запроса будет создано представление с названием `PlanetsView` которое будет содержать в себе только значения столбцов `PlanetName` и `OpeningYear`.
```sql
SELECT * FROM PlanetsView
```
Результат :

PlanetName	|OpeningYear
|:---:|:---:|
Mars	|1659
Saturn	|—
Neptune	|1846
Mercury	|1631
Venus	|1610

[к оглавлению](#SQL)

## `PRIMARY KEY`
Оператор `PRIMARY KEY` - это параметр, который устанавливается для однозначной идентификации записей в таблице. Значения `PRIMARY KEY` должны быть всегда уникальны, а также не содержать `NULL` значения.

Любая таблица _обязана_ иметь первичный ключ, по которому можно однозначно идентифицировать записи в ней.

[к оглавлению](#SQL)

#### Синтаксис оператора `PRIMARY KEY`
Оператор `PRIMARY KEY` имеет такой синтаксис :

Для MySQL :
```sql
CREATE TABLE table_name (
    Id int NOT NULL,
    PRIMARY KEY (Id)
)
```
Для MS SQL Server, Oracle, MS Access :
```sql
CREATE TABLE table_name (
    Id int NOT NULL PRIMARY KEY
)
```

[к оглавлению](#SQL)

#### Пример использования оператора `PRIMARY KEY`
__Задание__. Создать таблицу `Planets` с первичным ключом ID.
Решение для `MySQL` :
```sql
CREATE TABLE Planets (
    ID int,
    PlanetName varchar(10),
    Radius float (10),
    SunSeason float(10),
    OpeningYear int,
    HavingRings bit,
    Opener varchar(30),
    PRIMARY KEY (ID)
)
```
Решение для MS SQL Server, Oracle, MS Access (Для MySQL оно на самом деле тоже подходит) :
```sql
CREATE TABLE Planets (
    ID int PRIMARY KEY,
    PlanetName varchar(10),
    Radius float (10),
    SunSeason float(10),
    OpeningYear int,
    HavingRings bit,
    Opener varchar(30)
)
```

[к оглавлению](#SQL)

## `FOREIGN KEY`
Оператор `FOREIGN KEY` служит для указания в одной таблице на первичный ключ из другой таблицы.

[к оглавлению](#SQL)

#### Синтаксис оператора `FOREIGN KEY`
Оператор `FOREIGN KEY` имеет такой синтаксис :

Для MySQL :
```sql
CREATE TABLE table_1 (
    ID_1 int,
    ID_2 int,
    PRIMARY KEY (ID_1),
    FOREIGN KEY (ID_2) REFERENCES table_2(ID_2)
)
```
Для MS SQL Server, Oracle, MS Access :
```sql
CREATE TABLE table_1 (
    ID_1 int NOT NULL PRIMARY KEY,
    ID_2 int FOREIGN KEY REFERENCES table_2(ID_2)
)
```

[к оглавлению](#SQL)

#### Пример использования оператора `FOREIGN KEY`
__Задание__. Создать две таблицы, первая - `Authors`, содержащая 2 столбца, `AuthorID` и `AuthorName`, где `AuthorID` будет первичным ключом. Вторая таблица называется `Books` и содержит поля `BookID`, которое является вторичным ключом, ссылающимся на `Authors.AuthorID` и `BookName`.
```sql
CREATE TABLE Authors (
    AuthorID int AUTO_INCREMENT PRIMARY KEY,
    AuthorName varchar(30)
);

CREATE TABLE Books (
    BookID int,
    BookName varchar(30),
    FOREIGN KEY (BookID) REFERENCES Authors(AuthorID)
)
```
В результате выполнения этих двух запросов и добавления записей таблицы будут выглядеть вот так :

`Authors` : 

AuthorID	|AuthorName
|:---:|:---:|
1	|Bruce Eckel
2	|Robert Lafore
3	|Andrew Tanenbaum

`Books` : 

BookID	|BookName
|:---:|:---:|
3	|Modern Operating System
2	|Object-Oriented Programming in C++
1	|Thinking in Java
3	|Computer Architecture

[к оглавлению](#SQL)

## `UNION`
Оператор `UNION` используется для объединения двух и более запросов оператора `SELECT`.

[к оглавлению](#SQL)

Важно отметить, что все запросы, связываемые с помощью `UNION`, должны иметь одинаковое количество столбцов и типы возвращаемых данных, иначе произойдет ошибка при формировании результирующей таблицы.

 #### Синтаксис оператора `UNION`
 Оператор `UNION` имеет такой синтаксис :
```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2
```

[к оглавлению](#SQL)

#### Пример использования оператора `UNION`
Имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Задание__. Вывести имена исполнителей и их альбомов с помощью `UNION`.
```sql
SELECT Singer FROM Artists
UNION
SELECT Album FROM Artists
```
Результат :

Singer|	Album
|:---:|:---:|
The Prodigy|	Invaders Must Die
Drowning Pool|	Sinner
Massive Attack|	Mezzanine
The Prodigy|	Fat of the Land
The Prodigy|	Music For The Jilted Generation
Massive Attack|	100th Window
Drowning Pool|	Full Circle
Massive Attack|	Danny The Dog
Drowning Pool|	Resilience

[к оглавлению](#SQL)

## `LIMIT`
Оператор `LIMIT` позволяет вывести указанное количество строк из результата запроса.

Оператор `LIMIT` всегда пишется в конце запроса.

Используется в `MySQL`. Аналогом в `MS SQL` является оператор `TOP`.

[к оглавлению](#SQL)

#### Синтаксис оператора `LIMIT`
Оператор `LIMIT` имеет такой синтаксис :
```sql
LIMIT first_row [, last_row]
```
Оператор `LIMIT` выводит то количество записей, которое указано в параметре `first_row`. Если же указан еще и параметр `last_row`, то выводятся строки с `first_row` по `last_row` включительно.

[к оглавлению](#SQL)

#### Примеры использования оператора `LIMIT`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Задание 1__. Вывести первые `2` записи из таблицы.
```sql
SELECT *
FROM Universities
LIMIT 2
```
Результат :

ID	|UniversityName|	Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University|	12400	|12|	1229	|Perm	|psu.ru
2	|Saint Petersburg State University|	21300|	24|	13126|	Saint-Petersburg|	 spbu.ru

__Пример 2__. Вывести названия университетов из таблицы с `4` - го по `6` - й.
```sql
SELECT UniversityName
FROM Universities
LIMIT 4, 6
```
Результат :

UniversityName|
|:---:|
Moscow State University|
Higher School of Economics|
Ural Federal University|

[к оглавлению](#SQL)

## `IN`
Оператор `IN` позволяет определить, совпадает ли значение объекта со значением в списке.

[к оглавлению](#SQL)

#### Синтаксис оператора `IN`
Оператор `IN` имеет такой синтаксис :
```sql
expression [ NOT ] IN ( expression, [...] )
```

[к оглавлению](#SQL)

#### Пример использования оператора `IN`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Задание__. Вывести записи университетов из Новосибирска и Перми.
```sql
SELECT *
FROM Universities
WHERE Location IN ('Novosibirsk', 'Perm')
```
Этот запрос аналогичен :
```sql
SELECT *
FROM Universities
WHERE Location = 'Novosibirsk' 
OR Location = 'Perm'
```
Таким образом, если значений много, то удобнее их перечислить в `IN`.

Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400	|12	|1229	|Perm	|psu.ru
3	|Novosibirsk State University	|7200	|13	|1527	|Novosibirsk	|nsu.ru

[к оглавлению](#SQL)

## `TRUNCATE`
Оператор `TRUNCATE` служит для очистки таблицы от всех данных. Он аналогичен оператору `WHERE`, применяемому без оператора `WHERE`, но имеет такие основные отличия :
+ Оператор `TRUNCATE` не ведет запись об удаленных данных в журнал событий.
+ `DELETE` осуществляет блокировку построчно, а `TRUNCATE` - по всей странице целиком. Вследствие этого `TRUNCATE` не возвращает никакого значения, а `DELETE` возвращает количество удаленных строк.
+ После применения `DELETE` возможно сделать откат операции и восстановить удаленные данные (с помощью команды `ROLLBACK`). При применении оператора `TRUNCATE` этого сделать нельзя, однако этот оператор может применяться в тразакциях в том же MS SQL Server.
+ Как правило, реализация `TRUNCATE` отличается для каждый СУБД, поэтому информацию по его работе нужно искать в соответствующих документациях.

[к оглавлению](#SQL)

#### Синтаксис оператора `TRUNCATE`
Оператор `TRUNCATE` имеет такой синтаксис :
```sql
TRUNCATE TABLE table_name
```

[к оглавлению](#SQL)

#### Пример использования оператора `TRUNCATE`
Имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Задание__. Удалить все данные из таблицы.
```sql
TRUNCATE TABLE Artists
```
Как было сказано выше, аналогичную задачу можно решить и с использованием оператора `DELETE` без оператора `WHERE`.
```sql
DELETE FROM Artists
```

[к оглавлению](#SQL)

## `NOT`
Оператор `NOT` служит для задания противоположного условия. Является эквивалентом операции инверсии в математической логики и может применяться только к булевым значениям.

[к оглавлению](#SQL)

#### Синтаксис оператора `NOT`
Оператор `NOT` имеет такой синтаксис :
```sql
[ NOT ] boolean_expression
```

[к оглавлению](#SQL)

#### Примеры использования оператора `NOT`
Имеется следующая таблица `Artists` :

|Singer	|Album	|Year	|Sale|
|:----:|:---:|:---:|:---:|
|The Prodigy	|Invaders Must Die	|2008	|1200000|
|Drowning Pool	|Sinner	|2001	|400000|
|Massive Attack	|Mezzanine	|1998	|2300000|
|The Prodigy	|Fat of the Land	|1997	|600000|
|The Prodigy	|Music For The Jilted Generation	|1994	|1500000|
|Massive Attack	|100th Window	|2003	|1200000|
|Drowning Pool	|Full Circle	|2007	|800000|
|Massive Attack	|Danny The Dog	|2004	|1900000|
|Drowning Pool	|Resilience	|2013	|500000|

__Пример 1__. Вывести записи таблицы, в которых исполнитель не `Drowning Pool` и не `Massive Attack`.
```sql
SELECT *
FROM Artists
WHERE Singer NOT IN ('Drowning Pool', 'Massive Attack')
```
Результат :

Singer	|Album	|Year	|Sale
|:----:|:---:|:---:|:---:|
The Prodigy	|Invaders Must Die|	2008	|1200000
The Prodigy	|Fat of the Land|	1997|	600000
The Prodigy|	Music For The Jilted Generation|	1994|	1500000

Очевидно, что в данной ситуации можно было бы написать и так для получения того же результата :
```sql
SELECT *
FROM Artists
WHERE Singer = 'The Prodigy'
```
Но если бы в таблице было много других записей, то этот способ бы уже стал некорректным.

Таким образом, оператор `NOT` подходит как нельзя лучше для получения выборки исключающих множеств.

__Пример 2__. Вывести записи таблицы, в которых название альбома содержит одно слово.
```sql
SELECT *
FROM Artists
WHERE Album NOT LIKE '% %'
```
Результат :

Singer	|Album	|Year|	Sale
|:----:|:---:|:---:|:---:|
Drowning Pool	|Sinner	|2001	|400000
Massive Attack|	Mezzanine	|1998|	2300000
Drowning Pool	|Resilience	|2013|	500000

[к оглавлению](#SQL)

## `AS`
Оператор `AS` используется для переименования результирующих столбцов при выборке элементов.

[к оглавлению](#SQL)

#### Синтаксис оператора `AS`
Оператор `AS` имеет такой синтаксис :
```sql
SELECT column_name AS new_column_name FROM table_name
```

[к оглавлению](#SQL)

#### Пример использования оператора `AS`

Предположим, у нас есть таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener |
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88 |1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Задание__. Вывести среднее значение радиуса планет таблицы.
```sql
SELECT AVG(Radius) AS AverageRadius FROM Planets
```
Результат :

AverageRadius|
|:----:|
19383,6|

Результирующий столбец стал называться `AverageRadius`. Без использования оператора `AS`, столбец имел бы название `AVG(Radius)`, что смотрелось бы менее информативно.

[к оглавлению](#SQL)

`LIKE`
Оператор `LIKE` помогает задать шаблон в виде символьной строки.

[к оглавлению](#SQL)

#### Синтаксис оператора `LIKE`
Оператор `LIKE` имеет такой синтаксис :
```sql
expression [ NOT ] LIKE pattern
```
Тут `expression` - это любое символьное выражение, а `pattern` - это шаблон, по которому будет происходить проверка выражения `expression`. 

Шаблон может в себя включать такие спецсимволы :

Символ	|Описание	|Примеры
|:----:|:---------:|:-----:|
%	|Строка любой длины	|Пример 1
_	|Любой одиночный символ	|Пример 2
[]	|Диапазон или последовательность символов	|Пример 3
[^]	 |Исключающий диапазон или последовательность символов	|Пример 4

[к оглавлению](#SQL)

#### Примеры использования оператора `LIKE`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Вывести записи университетов, имеющих в своем названии слово `State`.
```sql
SELECT *
FROM Universities
WHERE UniversityName LIKE '%State%'
```
Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University|	12400	|12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300	|24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200	|13	|1527	|Novosibirsk	|nsu.ru
4	|Moscow State University	|35100	|39	|14358	|Moscow	|msu.ru

В этом примере, в качестве шаблона оператора `LIKE` послужил `%State%`. Исходя из условия задачи, слово `State` может стоять в названии где угодно, поэтому оно обрамлено символом `%`, обозначающим строку любой длины перед и после слова.

__Пример 2__. Вывести записи университетов, доменное имя сайтов которых содержит 4 символа(за исключением `.ru`).
```sql
SELECT *
FROM Universities
WHERE Site LIKE '____.ru'
```
Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
2	|Saint Petersburg State University	|21300	|24	|13126	|Saint-Petersburg	 |spbu.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg	|urfu.ru

__Пример 3__. Вывести записи университетов, первая буква доменного имени сайта которых содержит буквы из диапазона `[k-o]`.
```sql
SELECT *
FROM Universities
WHERE Site LIKE '[k-o]%'
```
Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4	|Moscow State University	|35100	|39	|14358	|Moscow	|msu.ru
7	|National Research Nuclear University|	8600	|10	|936	|Moscow	|mephi.ru

__Пример 4__. Вывести записи университетов, вторая буква названия города которых не входит в диапазон `[e-o]`.
```sql
SELECT *
FROM Universities
WHERE Location LIKE '_[^e-o]%'
```
Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
2	|Saint Petersburg State University	|21300	|24	|13126	|Saint-Petersburg	 |spbu.ru

[к оглавлению](#SQL)

## `BETWEEN`
Оператор `BETWEEN` задает диапазон для проверки условия.

[к оглавлению](#SQL)

#### Синтаксис оператора `BETWEEN`
Оператор `BETWEEN` имеет такой синтаксис :
```sql
test_expression [NOT] BETWEEN begin_expression AND end_expression
```
Значение переменных :
+ `test-expression` - задает объект для проверки по диапазону.
+ `begin-expression` - начальное значение диапазона.
+ `end-expression` - конечное значение диапазона.

[к оглавлению](#SQL)

#### Примеры использования оператора `BETWEEN`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Вывести записи тех университетов, число студентов в которых от 10000 до 30000.
```sql
SELECT *
FROM Universities
WHERE Students BETWEEN 10000 AND 30000
```
Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400	|12	|1229	|Perm|	psu.ru
2	|Saint Petersburg State University|	21300|	24	|13126|	Saint-Petersburg	| spbu.ru
5	|Higher School of Economics	|20335	|12	|1615|	Moscow|	hse.ru

Данный пример можно также записать и с помощью операторов сравнения + `WHERE`, код будет выглядеть так :
```sql
SELECT *
FROM Universities
WHERE Students >= 10000 AND Students <= 30000
```

__Пример 2__. Вывести записи университетов, число преподавателей в которых меньше 2000 или больше 14000.
```sql
SELECT *
FROM Universities
WHERE Professors NOT BETWEEN 2000 AND 14000
```
Результат :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University|	12400|	12	|1229|	Perm|	psu.ru
3	|Novosibirsk State University|	7200|	13	|1527	|Novosibirsk	|nsu.ru
4	|Moscow State University|	35100|	39	|14358|	Moscow	|msu.ru
5	|Higher School of Economics|	20335	|12	|1615|	Moscow|	hse.ru
7	|National Research Nuclear University|	8600|	10|	936|	Moscow	|mephi.ru

[к оглавлению](#SQL)

## `GRANT`
Оператор `GRANT` используется для назначения привилегий пользователям.

[к оглавлению](#SQL)

### Синтаксис оператора `GRANT`

![alt text](https://sql-language.ru/wp-content/uploads/2009/11/clip_image002.gif)

Здесь :
+ `system_priv` - системная привилегия
+ `role` - роль - набор соответствующих полномочий, которые администратор может коллективно предоставлять пользователям и другим ролям.
+ `user` - пользователь
+ `PUBLIC` - привилегия передается всем пользователям
+ `WITH ADMIN OPTION` - если предоставлены системные полномочия или роли, то параметр позволяет пользователю передать полномочие или роль другим пользователям или ролям

```sql
GRANT { ALL [ PRIVILEGES ] }
      | permission [ ( column [ ,...n ] ) ] [ ,...n ]
      [ ON [ class :: ] securable ] TO principal [ ,...n ]
      [ WITH GRANT OPTION ] [ AS principal ]
```

[к оглавлению](#SQL)

### Примеры использования оператора `GRANT`

__Пример 1__. Пользователь `P1` является владельцем таблицы `Students`. Необходимо передать пользователю `P2' право на осуществление запросов на выборку к этой таблице.
```sql
GRANT SELECT ON Students TO P2
```

__Пример 2__. Пользователь `P1` является владельцем таблицы `Students`. Необходимо передать пользователю `P2` право на вставку записей в эту таблицу.
```sql
GRANT INSERT ON Students TO P2
```

__Пример 3__. Необходимо передать пользователям `P2` и `P3` права на осуществление запросов на выборку и вставку записей в таблицу `Students`.
```sql
GRANT SELECT, INSERT ON Students TO P2, P3
```

__Пример 4__. Необходимо разрешить пользователю `P2` изменять значения столбцов `Fall` и `Ball` в таблице `Students`.
```sql
GRANT UPDATE(Fall, Ball) ON Students TO P2
```

__Пример 5__. Необходимо предоставить все полномочия таблицы `Students` пользователю `P2`.
```sql
GRANT ALL ON Students TO P2
```

__Пример 6__. Необходимо разрешить всем пользователям делать запросы на выборку к таблице `Students`.
```sql
GRANT SELECT ON Students TO PUBLIC
```

__Пример 7__. Необходимо разрешить вставлять записи и делать запросы на выборку к таблице `Students` пользователю `P2`, а также дать ему возможность передавать права на нее.
```sql
GRANT SELECT, INSERT ON Students TO P2 WITH GRANT OPTION
```

[к оглавлению](#SQL)

## `DENY`
Оператор `DENY` используется для удаления полномочий пользователя. Удаляются его персональные полномочия, а также с этого момента он не может пользоваться полномочиями своей группы.

[к оглавлению](#SQL)

### Синтаксис оператора `DENY`
```sql
DENY {ALL  [PRIVILEGES]} | permission_list
 [ON  [class::]  securable] TO principal_list
 [CASCADE]   [ AS principal ]
```

[к оглавлению](#SQL)

### Примеры использования оператора `DENY`

__Пример 1__. Забрать у пользователя `P2` возможность вставлять записи в таблицу `Students`.
```sql
DENY INSERT ON Students TO P2
```

__Пример 2__. Забрать у пользователя `P2` возможность создавать таблицы.
```sql
DENY CREATE TABLE TO P2
```

[к оглавлению](#SQL)

## `REVOKE`
Оператор `REVOKE` используется для отмены привилегий пользователя или группы.

[к оглавлению](#SQL)

### Синтаксис оператора `REVOKE`
```sql
REVOKE [ GRANT OPTION FOR ]
    { { SELECT | INSERT | UPDATE | DELETE | TRUNCATE | REFERENCES | TRIGGER }
    [, ...] | ALL [ PRIVILEGES ] }
    ON { [ TABLE ] имя_таблицы [, ...]
         | ALL TABLES IN SCHEMA имя_схемы [, ...] }
    FROM указание_роли [, ...]
    [ CASCADE | RESTRICT ]
```
Это только один из возможных синтаксисов, в остальных как правило меняется только объект полномочий, то есть секция после `ON`.

[к оглавлению](#SQL)

### Примеры использования оператора `REVOKE`

__Пример 1__. Забрать у пользователя `P2` возможность создавать таблицы.
```sql
REVOKE CREATE TABLE FROM P2
```

__Пример 2__. Забрать у пользователя `P2` возможность делать выборки из таблицы `Students`.
```sql
REVOKE SELECT ON Students FROM P2
```

__Пример 3__. Забрать у пользователя `P2` возможность удаления и изменения записей в таблице `Students`.
```sql
REVOKE DELETE, UPDATE ON Students FROM P2
```

__Пример 4__. Отменить всех привилегий в таблице `Students` для всех пользователей.
```sql
REVOKE ALL ON Students FROM PUBLIC
```

[к оглавлению](#SQL)

## `COUNT`
Оператор `COUNT()` - это функция, которая возвращает количество записей (строк) в таблице. Запись функции с указанием столбца в качестве аргумента вернет количество записей конкретного столбца за исключением `NULL` записей.

[к оглавлению](#SQL)

#### Синтаксис функции `COUNT`
Функция `COUNT` имеет такой синтаксис :
```sql
COUNT(column_name)
```
Запись функции с указанием маски `*` вернет количество строк в таблице. Её синтаксис :
```sql
COUNT(*)
```

[к оглавлению](#SQL)

#### Примеры использования функции `COUNT`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Вывести число записей таблицы.
```sql
SELECT COUNT(*) 
FROM Universities
```
Вывод : `7`

__Пример 2__. Найти количество университетов, расположенных в `Москве` :
```sql
SELECT COUNT(*)
FROM Universities
WHERE Location = 'Moscow'
```
Вывод : `3`

__Пример 3__. Найти количество университетов с более чем `20` факультетами.
```sql
SELECT COUNT(*)
FROM Universities
WHERE Faculties > 20
```
Вывод : `2`

[к оглавлению](#SQL)

## `AVG`
Оператор `AVG` - это функция, возвращающая среднее значения столбца. Важным является то, что она применима ТОЛЬКО для числовых стобцов.

[к оглавлению](#SQL)

#### Синтаксис функции `AVG`
Функция `AVG` имеет такой синтаксис :
```sql
AVG(column_name)
```

[к оглавлению](#SQL)

#### Примеры использования функции `AVG`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Найти среднее число студентов всех университетов.
```sql
SELECT AVG(Students)
FROM Universities
```
Вывод : `23133`

__Пример 2__. Найти среднее число факультетов в университетах Москвы.
```sql
SELECT AVG(Faculties)
FROM Universities
WHERE Location = 'Moscow'
```
Вывод : `20`

[к оглавлению](#SQL)

## `MIN`
Оператор `MIN` - это функция, возвращающая минимальное значение столбца.

[к оглавлению](#SQL)

#### Синтаксис функции `MIN`
Функция `MIN` имеет такой синтаксис :
```sql
MIN(column_name)
```

[к оглавлению](#SQL)

#### Примеры использования функции `MIN`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Найти минимальное значение столбца `Professors`.
```sql
SELECT MIN(Professors)
FROM Universities
```
Вывод : `936`

__Пример 2__. Найти минимальное количество студентов в любом из университетов Москвы.
```sql
SELECT MIN(Students)
FROM Universities
WHERE Location = 'Moscow'
```
Вывод : `8600`

__Пример 3__. Найти город, в котором находится университет с наименьшим количеством студентов.
```sql
SELECT Location
FROM Universities
WHERE Students = (SELECT MIN(Students) FROM Universities)
```
Вывод : `Novosibirsk`

[к оглавлению](#SQL)

## `MAX`
Оператор `MAX` - это функция, возвращающая максимальное значение столбца.

[к оглавлению](#SQL)

#### Синтаксис функции `MAX`
Функция `MAX` имеет такой синтаксис :
```sql
MAX(column_name)
```

[к оглавлению](#SQL)

#### Примеры использования функции `MAX`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Найти максимальное значение колонки `Students`.
```sql
SELECT MAX(Students)
FROM Universities
```
Вывод : `57000`

__Пример 2__. Найти максимальное количество факультетов в университете среди университетов Санкт-Петербурга
```sql
SELECT MAX(Faculties)
FROM Universities
WHERE Location = 'Saint-Petersburg'
```
Вывод : `24`

__Пример 3__. Найти имя университета с наибольшим числом преподавателей.
```sql
SELECT UniversityName
FROM Universities
WHERE Professors = (SELECT MAX(Professors) FROM Universities)
```
Вывод : `Moscow State University`

[к оглавлению](#SQL)

## `SUM`
Оператор `SUM` - это функция, возвращающая сумму значений столбца. Применима ТОЛЬКО для числовых столбцов.

[к оглавлению](#SQL)

#### Синтаксис функции `SUM`
Функция `SUM` имеет такой синтаксис :
```sql
SUM ( [ALL | DISTINCT] expression )
```
Параметр `ALL` тут является параметром по умолчанию. Считается сумма всех строк.

При указании параметра `DISTINCT` происходит суммирование только уникальных значений.

[к оглавлению](#SQL)

#### Примеры использования функции `SUM`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Пример 1__. Найти количество студентов всех университетов в таблице.
```sql
SELECT SUM(Students)
FROM Universities
```
Вывод : `161935`

__Пример 2__. Найти количество преподавателей московских университетов.
```sql
SELECT SUM(Professors)
FROM Universities
WHERE Localion = 'Moscow'
```
Вывод : `16909`

__Пример 3__. Произвести подсчет уникальных значений столбца `Faculties`.
```sql
SELECT SUM(DISTINCT Faculties)
FROM Universities
```
Вывод : `117`, потому что в столбце `Faculties` присутствует две одинаковых записи `Faculties` под `ID = 1` и `ID = 5`, и в подсчет входит только одно из этих значений.

[к оглавлению](#SQL)

## `ROUND`
Оператор `ROUND` - это функция для округления десятичных чисел. Работает она ТОЛЬКО с числовыми столбцами или произвольными вещественными числами.

[к оглавлению](#SQL)

#### Синтаксис функции `ROUND`
Функция `ROUND` имеет такой синтаксис :
```sql
ROUND(expression, length)
```
Тут `expression` - это название столбца или столбцов, а также вещественное число.

`lenth` - указывает точность округления для числа.

[к оглавлению](#SQL)

#### Примеры использования функции `ROUND`
Предположим, у нас есть таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener |
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88 |1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 1__. Округлить столбец `SunSeason` с точностью до одного знака после запятой.
```sql
SELECT ROUNT(SunSeason, 1)
FROM Planets
```
Результат :

SunSeason|
|:----:|
687.5|
10759.2|
60190.9|
115.8|
243.5|

__Пример 2__. Округлить значение числа.
Функция `ROUND()` может принимать в качестве первого аргумента любое вещественное число.
```sql
SELECT ROUNT (43532.8123, 3)
```
Результат : `45532.8`

[к оглавлению](#SQL)

## `UCASE`
Оператор `UCASE` - это функция, возвращающая значение столбца или столбцов в верхнем регистре букв.

[к оглавлению](#SQL)

#### Синтаксис функции `UCASE`
Функция `UCASE` имеет такой синтаксис :
```sql
UCASE(column_name)
```
В СУБД MS SQL Server аналогом этой функции является функция `UPPER` с аналогичным синтаксисом.

[к оглавлению](#SQL)

#### Примеры использования функции `UCASE`
Предположим, у нас есть таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener |
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88 |1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 1__. Вывести названия планет в верхнем регистре, у которых нет названия колец.
```sql
SELECT UCASE(PlanetName)
FROM Planets
WHERE HavingRings = 'No'
```
Результат :

PlanetName|
|:----:|
MARS|
MERCURY|
VENUS|

__Пример 2__. Вывести названия планет в верхнем регистре, радиус которых больше 20000.
```sql
SELECT UCASE(PlanetName)
FROM Planets
WHERE Radius > 20000
```
Результат :

PlanetName|
|:----:|
SATURN|
NEPTUNE|

[к оглавлению](#SQL)

## `LCASE`
Оператор `LCASE` - это функция, возвращающая значение столбца или столбцов в нижнем регистре букв.

[к оглавлению](#SQL)

#### Синтаксис функции `LCASE`
Функция `LCASE` имеет такой синтаксис :
```sql
LCASE(column_name)
```
В СУБД MS SQL Server аналогом этой функции является функция `LOWER` с аналогичным синтаксисом.

[к оглавлению](#SQL)

#### Примеры использования функции `LCASE`
Предположим, у нас есть таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener |
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88 |1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 1__. Вывести названия планет в нижнем регистре, у которых есть кольца.
```sql
SELECT LCASE(PlanetName)
FROM Planets
WHERE HavingRings = 'Yes'
```
Результат :

PlanetName|
|:----:|
SATURN|
NEPTUNE|

__Пример 2__. Вывести в нижнем регистре имена первооткрывателей планет, открытых до 1650 года.
```sql
SELECT LCASE(Opener)
FROM Planets
WHERE OpeningYear < 1650
```
Результат :

Opener|
|:----:|
Nicolaus Copernicus|
Galileo Galilei|

[к оглавлению](#SQL)

## `LEN`
Оператор `LEN` - это функция, возвращающая длину значения в поле записи. Работает как для чисел, так и для строк.

Функция `LEN` исключает конечные пробелы из подсчета.

[к оглавлению](#SQL)

#### Синтаксис функции `LEN`
Функция `LEN` имеет такой синтаксис :
```sql
LEN(column_name)
```

[к оглавлению](#SQL)

#### Примеры использования функции `LEN`
Предположим, у нас есть таблица `Planets` :

|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener |
|:----:|:---------:|:-----:|:---------:|:-------------:|:-------------:|:----:|
|1	|Mars	|3396	|687	|1659	|No	|Christian Huygens|
|2	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|3	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
|4	|Mercury	|2439	|115.88 |1631	|No	|Nicolaus Copernicus|
|5	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|

__Пример 1__. Вывести всех первооткрывателей планет и длины названий открытых ими планет.
```sql
SELECT Opener, LEN(PlanetName)
FROM Planets
```
Результат :

Opener	|LEN(PlanetName)
|:-------------:|:----:|
Christiaan Huygens|	4
—	|6
John Couch Adams|	7
Nicolaus Copernicus|	7
Galileo Galilei|	5

__Пример 2__. Вывести разрядность числа радиуса и название планет имеющих кольца.
```sql
SELECT PlanetName, LEN(Radius)
FROM Planets
WHERE HavingRings = 'Yes'
```
Результат :

PlanetName	|LEN(Radius)
|:-------------:|:----:|
Saturn	|6
Neptune	|6

[к оглавлению](#SQL)

## `MID`
Оператор `MID` - это функция, выводящая определенное количество символов текстового поля таблицы.

[к оглавлению](#SQL)

#### Синтаксис функции `MID`
Функция `MID` имеет такой синтаксис :
```sql
MID(colunm_name,start [,length])
```
Параметр `start` задает позицию начального символа.

Параметр `length` устанавливает количество символов для вывода, начиная с позиции, указанной в параметре `start`.

[к оглавлению](#SQL)

#### Пример использования функции `MID`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Задание__. Вывести первые `3` символа каждого из названий городов.
```sql
SELECT MID(Location, 1, 3)
FROM Universities
```
Результат :

Location|
|:---:|
Per|
Sai|
Nov|
Mos|
Mos|
Yek|
Mos|

[к оглавлению](#SQL)

## `NOW`
Оператор `NOW` - это функция, возвращающая системные время и дату.

[к оглавлению](#SQL)

#### Синтаксис функции `NOW`
Функция `NOW` имеет такой синтаксис :
```sql
NOW()
```

[к оглавлению](#SQL)

#### Пример использования функции `NOW`
Имеется следующая таблица `Universities` :

ID	|UniversityName	|Students	|Faculties	|Professors	|Location	|Site
|:----:|:---:|:---:|:---:|:----:|:---:|:---:|
1	|Perm State National Research University	|12400|	12	|1229	|Perm	|psu.ru
2	|Saint Petersburg State University	|21300|	24|	13126	|Saint-Petersburg	| spbu.ru
3	|Novosibirsk State University	|7200|	13	|1527	|Novosibirsk	|nsu.ru
4|	Moscow State University	|35100|	39	|14358	|Moscow	|msu.ru
5	|Higher School of Economics	|20335	|12	|1615	|Moscow|	hse.ru
6	|Ural Federal University	|57000	|19	|5640	|Yekaterinburg|	urfu.ru
7	|National Research Nuclear University	|8600	|10	|936	|Moscow|	mephi.ru

__Задание__. Вывести сколько на текущее время обучается студентов в каждом университете, при этом чтобы было указано текущее время и дата.
```sql
SELECT UniversityName, Students, NOW() AS CurrentTime
FROM Universities
```
Результат :

UniversityName	|Students	|CurDate
|:----:|:---:|:---:|
Perm State National Research University	|12400	|6/26/2013 2:11:07 PM
Saint Petersburg State University	|21300	|6/26/2013 2:11:07 PM
Novosibirsk State University	|7200	|6/26/2013 2:11:07 PM
Moscow State University	|35100	|6/26/2013 2:11:07 PM
Higher School of Economics	|20335	|6/26/2013 2:11:07 PM
Ural Federal University	|57000	|6/26/2013 2:11:07 PM
National Research Nuclear University	|8600	|6/26/2013 2:11:07 PM

[к оглавлению](#SQL)
