## SQL
+ [Что такое _SQL_?](#Что-такое-SQL)
+ [Из чего состоит _SQL_?](#Из-чего-состоит-SQL)
+ [`CREATE`](#CREATE)
    + [Синтаксис оператора `CREATE TABLE`](#Синтаксис-оператора-CREATE TABLE)
    + [Пример использования оператора `CREATE TABLE`](#Пример-использования-оператора-CREATE-TABLE)
+ [`ALTER TABLE`](#ALTER TABLE)
    + [Синтаксис оператора `ALTER TABLE`](#Синтаксис-оператора-ALTER-TABLE)
    + [Пример использования оператора `ALTER TABLE`](#Пример-использования-оператора-ALTER-TABLE)
+ [`DROP`](#DROP)
    + [Синтаксис оператора `DROP`](#Синтаксис-оператора-DROP)
    + [Пример использования оператора `DROP TABLE`](#Пример-использования-оператора-DROP-TABLE)
    + [Пример использования оператора `DROP DATABASE`](#Пример-использования-оператора-DROP-DATABASE)
    
## Что такое _SQL_?
_SQL_ (Structured Query Language) - это язык структурированных запросов, который используется для управления реляционными базами данных и данными в них.

[к оглавлению](#SQL)

### Из чего состоит _SQL_?
_SQL_ состоит из `4`-х частей :
+ __DDL__ (Data Definition Language) - это работа со структурой БД. В нее входят такие операторы как :
    + `CREATE` (Создание)
    + `ALTER` (Изменение)
    + `DROP` (Удаление)
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
