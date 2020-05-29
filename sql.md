## SQL
+ [Что такое _SQL_?](#Что-такое-SQL)
+ [Из чего состоит _SQL_?](#Из-чего-состоит-SQL)
+ [`CREATE`](#CREATE)
    + [Синтаксис оператора `CREATE TABLE`](#Синтаксис-оператора-CREATE-TABLE)
    + [Пример использования оператора `CREATE TABLE`](#Пример-использования-оператора-CREATE-TABLE)
+ [`ALTER TABLE`](#ALTER-TABLE)
    + [Синтаксис оператора `ALTER TABLE`](#Синтаксис-оператора-ALTER-TABLE)
    + [Пример использования оператора `ALTER TABLE`](#Пример-использования-оператора-ALTER-TABLE)
+ [`DROP`](#DROP)
    + [Синтаксис оператора `DROP`](#Синтаксис-оператора-DROP)
    + [Пример использования оператора `DROP TABLE`](#Пример-использования-оператора-DROP-TABLE)
    + [Пример использования оператора `DROP DATABASE`](#Пример-использования-оператора-DROP-DATABASE)
+ [`SELECT`](#SELECT)
    + [Синтаксис оператора `SELECT`](#Синтаксис-оператора-SELECT)
    + [Примеры использования оператора `SELECT`](#Примеры-использования-оператора-SELECT)
+ [`INSERT`](#INSERT)
    + [Синтаксис оператора `INSERT`](#Синтаксис-оператора-INSERT)
    + [Примеры использования оператора `INSERT`](#Примеры-использования-оператора-INSERT)
    
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
    + `INSERT`
    + `SELECT`
    + `UPDATE`
    + `DELETE`
+ __DCL__ (Data Control Language) - это работа с правами. В нее входят такие операторы как :
    + `GRANT`
    + `DENY`
    + `REVOKE`
+ __TCL__ (Transaction Control Language) - это работа с транзакциями. В нее входят такие операторы как :
    + `BEGIN TRANSACTION`
    + `COMMIT`
    + `ROLLBACK`

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
|ID	|PlanetName	|Radius	|SunSeason	|OpeningYear	|HavingRings	|Opener|
|:-----:|:---:|:---:|:----:|:----:|:---:|:---:|
|1|	Mars	|3396	|687	|1659	|No	|Christiaan Huygens|
|2	|Mercury	|2439	|115.88	|1631	|No	|Nicolaus Copernicus|
|3	|Venus	|6051	|243	|1610	|No	|Galileo Galilei|
|1	|Saturn	|60268	|10759.22	|—	|Yes	|—|
|2	|Neptune	|24764	|60190	|1846	|Yes	|John Couch Adams|
Как видим, все значения из таблицы `PlanetsWithRings` вставились в таблицу `PlanetsWithoutRings`.

[к оглавлению](#SQL)
