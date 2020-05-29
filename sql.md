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
+ [`UPDATE`](#UPDATE)
    + [Синтаксис оператора `UPDATE`](#Синтаксис-оператора-UPDATE)
    + [Примеры использования оператора `UPDATE`](#Примеры-использования-оператора-UPDATE)
+ [`DELETE`](#DELETE)
    + [Синтаксис оператора `DELETE`](#Синтаксис-оператора-DELETE)
    + [Примеры использования оператора `DELETE`](#Примеры-использования-оператора-DELETE)
+ [`WHERE`](#WHERE)
    + [Синтаксис оператора `WHERE`](#Синтаксис-оператора-WHERE)
    + [Примеры использования оператора `WHERE`](#Примеры-использования-оператора-WHERE)
+ [`GROUP BY`](#GROUP-BY)
    + [Синтаксис оператора `GROUP BY`](#Синтаксис-оператора-GROUP-BY)
    + [Примеры использования оператора `GROUP BY`](#Примеры-использования-оператора-GROUP-BY)
+ [`HAVING`](#HAVING)
    + [Синтаксис оператора `HAVING`](#Синтаксис-оператора-HAVING)
    + [Примеры использования оператора `HAVING`](#Примеры-использования-оператора-HAVING)
+ [`ORDER BY`](#ORDER-BY)
    + [Синтаксис оператора `ORDER BY`](#Синтаксис-оператора-ORDER-BY)
    + [Примеры использования оператора `ORDER BY`](#Примеры-использования-оператора-ORDER-BY)
+ [`DISTINCT`](#DISTINCT)
    + [Синтаксис оператора `DISTINCT`](#Синтаксис-оператора-DISTINCT)
    + [Примеры использования оператора `DISTINCT`](#Примеры-использования-оператора-DISTINCT)
+ [`AND` и `OR`](#AND)
    + [Синтаксис оператора `AND`](#Синтаксис-оператора-AND)
    + [Синтаксис оператора `OR`](#Синтаксис-оператора-OR)
    + [Примеры использования операторов `AND` и `OR`](#Примеры-использования-операторов-AND-и-OR)
+ [`DEFAULT`](#DEFAULT)
    + [Синтаксис оператора `DEFAULT`](#Синтаксис-оператора-DEFAULT)
    + [Пример использования оператора `DEFAULT`](#Пример-использования-оператора-DEFAULT)
+ [`VIEW`](#VIEW)
    + [Синтаксис оператора `CREATE VIEW`](#Синтаксис-оператора-CREATE-VIEW)
    + [Пример использования оператора `CREATE VIEW`](#Пример-использования-оператора-CREATE-VIEW)
    
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
