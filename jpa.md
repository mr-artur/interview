# JPA
+ [Что такое _«ORM»_?](#Что-такое-ORM)
+ [Какие проблемы решает _ORM_ ?](#Какие-проблемы-решает-ORM)
+ [Какие преимущества дает ORM по сравнению с JDBC?](#Какие-преимущества-дает-ORM-по-сравнению-с-JDBC)
+ [Что такое _«JPA»_?](#Что-такое-JPA)
+ [Из чего состоит _«JPA»_?](#Из-чего-состоит-JPA)
+ [Чем отличается _JPA_ от _Hibernate_?](#Чем-отличается-JPA-от-Hibernate)
+ [Можно ли использовать _JPA_ с _NoSQL_ базами данных?](#Можно-ли-использовать-JPA-с-NoSQL-базами-данных)
+ [_JPQL_](#JPQL)
    + [Полиморфизм в _JPQL_](#Полиморфизм-в-JPQL)
+ [_Criteria API_](#Criteria-API)
+ [_Entity_](#Entity)
    + [Требования к _Entity_ классам в _JPA_](#Требования-к-Entity-классам-в-JPA)
    + [Типы данных, допустимые для атрибутов _Entity_ класса](#Типы-данных-допустимые-для-атрибутов-Entity-класса)
    + [Типы данных, допустимые для `Id` _Entity_ класса](#Типы-данных-допустимые-для-Id-Entity-класса)
+ [_Embeddable_ классы](#Embeddable-классы)
    + [Требования к _Embeddable_ классам в _JPA_](#Требования-к-Embeddable-классам-в-JPA)
+ [Типы связей между _Entity_](#Типы-связей-между-Entity)
+ [Типы _Fetch_ стратегии](#Типы-Fetch-стратегии)
+ [Mapped Superclass](#Mapped-Superclass)
+ [Стратегии наследования маппинга в JPA](#Стратегии-наследования-маппинга-в-JPA)
+ [`EntityManager`](#EntityManager)
    + [Методы `EntityManager`](#Методы-EntityManager)
+ [Состояния _Entity_ и переходы между ними](#Состояния-Entity-и-переходы-между-ними)
    + [Операция `persist` на _Entity_ в разных состояниях](#Операция-persist-на-Entity-в-разных-состояниях)
    + [Операция `merge` на _Entity_ в разных состояниях](#Операция-merge-на-Entity-в-разных-состояниях)
    + [Операция `remove` на _Entity_ в разных состояниях](#Операция-remove-на-Entity-в-разных-состояниях)
    + [Операция `detach` на _Entity_ в разных состояниях](#Операция-detach-на-Entity-в-разных-состояниях)
    + [Операция `refresh` на _Entity_ в разных состояниях](#Операция-refresh-на-Entity-в-разных-состояниях)
+ [Аннотации JPA ](#Аннотации-JPA )   
+ [Cascade Types в JPA](#Cascade-Types-в-JPA)
+ [`orphanRemoval`](#orphanRemoval)
+ [В чем отличие между `cascade=CascadeType.REMOVE` и `orphanRemoval=true`?](#В-чем-отличие-между-cascadeCascadeTypeREMOVE-и-orphanRemovaltrue)
+ [Callback методы](#Callback-методы)

## Что такое _«ORM»_?
_ORM_ (Object-Relational Mapping) - это технология программирования, которая служит для преобразовывания данных и их обмена между реляционной базой данных и Java. Данную концепцию воплощает спецификация _JPA_. 

[к оглавлению](#JPA)

## Какие проблемы решает _ORM_ ?
Все эти проблемы связаны с разницей между объектно-ориентированной моделью и реляционной моделью.
##### 1. Наследование.

В реляционной БД нет понятия, похожего на наследование, которое является одним из ключевых принципов ООП.

##### 2. Идентификация.

В БД мы можем идентифицировать сущность только по первичному ключу. В Java же это можно сделать с помощью сравнения ссылок (`==`), так и с помощью `equals`.

##### 3. Ассоциации.
В Java мы используем ссылки на объекты для ассоциации, а в БД - внешние ключи (foreign keys).

##### 4. Доступ.
В Java и в реляционной модели абсолютно разные способы получения доступа к объекту.

##### 5. Инкапсуляция
Крайне часто можно столкнуться с тем, что наша ОО модель имеет больше классов, чем таблиц в БД.

[к оглавлению](#JPA)

## Какие преимущества дает ORM по сравнению с JDBC?
+ Позволяет нашим бизнес-методам обращаться не к БД, а к Java-классам.
+ Ускоряет разработку приложения.
+ Основана на JDBC.
+ Отделяет SQL-запросы от ОО модели.
+ Позволяет не думать о реализации БД.
+ Сущности основаны на бизнес-задачах, а не на структуре БД.
+ Управление транзакциями.

[к оглавлению](#JPA)

## Что такое _«JPA»_?
+ _JPA_ (Java Persistence API) - это спецификация _ORM_ фреймворка в Java, которая описывает систему для хранения Java объектов в реляционных БД в удобном виде.
+ _JPA_ - это спецификация (документ, утвержденный как стандарт, описывающий все аспекты технологии), часть EJB3 спецификации.
+ Сам _JPA_ не умеет ни сохранять, ни управлять объектами. Он только определяет правила, по которым все будет работать. JPA также определяет интерфейсы, которые должны будут реализовываться провайдерами. Также JPA определяет, как должны описываться метаданные, и как должны работать провайдеры. Дальше, каждый провайдер, реализуя эту спецификацию, определяет получение, сохранение и управление объектами. У каждого провайдера реализация разная.
+ У JPA_ есть такие провайдеры :
    + Hibernate
    + Oracle TopLink
    + Apache OpenJPA
        
[к оглавлению](#JPA)

## Из чего состоит _«JPA»_?
_JPA_ состоит из `3`-х частей :
+ __API__ - это набор интерфейсов в пакете `javax.persistence`, которые помогают организовать взаимодействие с ORM провайдером.
+ __JPQL__ - это объектный язык запросов. Он очень похож на SQL, но запросы в нем выполняются в терминах объектов.
+ __Metadata__ - это набор аннотаций, которые мы можем использовать для описания метаданные отображений объектов. Это помогает _JPA_ узнать, какой объект в какую таблицу нужно сохранить. Метаданные описываются двумя способами :
    + через xml-файл
    + через аннотации

[к оглавлению](#JPA)

## Чем отличается _JPA_ от _Hibernate_?
Отличие в том, что _Hibernate_ - это один из самых популярных провайдеров, которые реализуют спецификацию _JPA_. То есть, _JPA_ описывает только правила и API системы хранения объектов, а _Hibernate_ реализует эти описания, при чем в _Hibernate_ есть также свои дополнительные возможности, которые не описаны в спецификации _JPA_.

[к оглавлению](#JPA)

## Можно ли использовать _JPA_ с _NoSQL_ базами данных?
Спецификация _JPA_ говорит только об отображении Java объектов в таблицы реляционных баз данных, но несмотря на это, есть ряд _ORM_ провайдеров для _NoSQL_ баз данных, реализующих _JPA_. Их примеры : 
+ Kundera
+ DataNucleus
+ ObjectDB

Естественно, при этом не все специфичные особенности спецификации именно для реляционных БД переносятся при этом на _NoSQL_ базы полностью.

[к оглавлению](#JPA)

## _JPQL_
+ _JPQL_ (Java Persistence Query Language) - это язык запросов в спецификации _JPA_, который похож на SQL, но при этом отличается тем, что его запросы записываются в терминах объектов.
+ Вместо имен и колонок таблиц данных, в _JPQL_ используются имена классов Entity, а также их атрибуты.
+ В качестве параметров запросов, в _JPQL_ также используются типы данных атрибутов Entity.
+ В отличии от SQL, в JPQL есть автоматический полиморфизм.
+ В JPQL есть функции, которых нету в SQL, такие как например :
    + `KEY` (ключ мапы)
    + `VALUE` (значение мапы)
    + `TREAT` (downcasting - приведение суперкласса к объекту - наследнику)
    + `ENTRY`
    + и т.д.
+ У JPQL есть два важных недостатка, которые решаются с помощью использования _Criteria API_ :
    + Запросы _JPQL_ жестко определяются на стадии компиляции и во время исполнения их не изменить.
    + Запросы _JPQL_ никак не связаны с реальными сущностями, и если сущность изменяется, то никто не скажет, что запрос больше неверен, до тех пор, пока его не попытаются выполнить.

[к оглавлению](#JPA)

### Полиморфизм в _JPQL_
+ Полиморфизм в _JPQL_ - это то, что каждый запрос к Entity возвращает не только объекты Entity, но и объекты всех наследников Entity, вне зависимости от стратегии наследования.
+ Например, запрос `SELECT * FROM Animal` вернет не только объекты класса `Animal`, но и объекты классов условных `Dog` и `Cat` - наследников `Animal`.
+ Чтобы отключить полиморфизм в _JPQL_, используется функция `TYPE` в `WHERE` - условии. Используется это так :
```jpaql
SELECT * FROM Animal a WHERE TYPE(a) IN (Animal, Cat)
```
Такой запрос уже не вернет объекты типа `Dog`.

[к оглавлению](#JPA)

## _Criteria API_
+ _Criteria API_ - это тоже язык запросов, похожий на _JPQL_, однако запросы в нем основаны на методах и объектах.
+ Запросы с помощью _Criteria API_ выглядят вот так :
![alt text](https://3.bp.blogspot.com/-HLFfj8qlqwE/Vvv8RVqXM-I/AAAAAAAAAeY/Qogvb2_Ie0o2NfFJCU5NVE7W4eYjYXloQ/s640/JPQL.jpg)
+ _Criteria Api_ помогает строить динамические и гибкие запросы к БД. Можно также сказать, что он решает такие две проблемы _JPQL_ :
    + Запросы _JPQL_ жестко определяются на стадии компиляции и во время исполнения их не изменить.
    + Запросы _JPQL_ никак не связаны с реальными сущностями, и если сущность изменяется, то никто не скажет, что запрос больше неверен, до тех пор, пока его не попытаются выполнить.

[к оглавлению](#JPA)

## _Entity_
+ _Entity_ - это легковесный хранимый объект бизнес-логики (persistent domain object).
+ Entity класс __может__ наследоваться от другого entity класса.
+ Класс, который не является entity, __может__ наследоваться от entity класса.
+ Entity __может__ наследовать от не-entity классов.
+ Entity __может__ быть абстрактным классом. При этом его все равно нельзя создать объекты именно этого класса (обычно используется для наследования).

[к оглавлению](#JPA)

## Требования к _Entity_ классам в _JPA_
1. Entity класс должен быть помечен аннотацией `@Entity` или описан в xml-конфигурации.
2. Entity класс должен содержать первичный ключ (`@Id`), то есть атрибут или группу атрибутов, которые определяют уникальность этой записи в БД.
3. Entity класс должен содержать `public` или `protected` конструктор без аргументов.
4. Entity класс должен быть классом верхнего уровня (top-level class). Это означает, что он не должен быть вложенным классом.
5. Entity класс не должен быть `enum` - ом или интерфейсом.
6. Entity класс не должен быть финальным классом (final class).
7. Entity класс не должен содержать финальные поля или методы, если они участвуют в маппинге.
8. Поля Entity класса должны быть `private`, с наличием сеттеров и геттеров к ним.
9. Если экземпляры Entity класса должны использоваться удаленно как отдельные объекты, то сам класс должен реализовать `Serializable`.

[к оглавлению](#JPA)

## Типы данных, допустимые для атрибутов _Entity_ класса
1. Примитивные типы и их обертки
2. Строки
3. Любые типы, имплементирующие `Serializable`
4. Enums
5. Entity types
6. Embeddable классы
7. Коллекции типов 1 - 6

[к оглавлению](#JPA)

## Типы данных, допустимые для `Id` _Entity_ класса
+ В случае, если ключ не автогенерируемый, можно использовать следующие типы данных для того, чтобы они работали в любой БД :
    1. Примитивные типы и их обертки.
    2. Строки
    3. BigDecimal и BigInteger.
    4. java.util.Date и java.sql.Date. 
    
+ В случае автогенерированого ключа, допустимы только числовые типы. В случае использования других типов данных в первичном ключе, он может работать только для некоторых баз данных, т.е., становится не переносимым.

[к оглавлению](#JPA)

## _Embeddable_ классы
+ _Embeddable_ класс (Встраиваемый) - это такой класс, который используется только как часть _Entity_ классов. 
+ В целом, такие классы служат для вынесения каких-то общих атрибутов из _Entity_ классов. То есть, можно считать, что _JPA_ просто встраивает в _Entity_ вместо объекта встраемового типа те атрибуты, которые он содержит.
+ _Entity_ могут содержать как одиночные объекты `Embeddable` классов, так и их коллекции.
+ _Embeddable_ классы могут быть использованы как ключи или значения _Map_.
+ Во время выполнения каждый _Embeddable_ объект принадлежит только одному экземпляру _Entity_, то есть, не может быть использован для передачи данных между _Entity_ объектами.
+ Каждый _Embeddable_ класс __может__ внутри содержать объекты других _Embeddable_ классов.
+ _Embeddable_ класс __может__  содержать связи с другими _Entity_ или их коллекциями, но только в случае, если такой класс не используется как первичный ключ или ключ map-ы.

[к оглавлению](#JPA)

## Требования к _Embeddable_ классам в _JPA_
1. Такие классы должны удовлетворять тем же требованиям, что и _Entity_, за исключением двух :
    + Они не обязаны содержать первичный ключ.
    + Они не обязаны быть отмечены аннотацией `@Entity`.
2. _Embeddable_ класс должен быть отмечен специальной аннотацией `@Embeddable` или быть описанным в xml-конфигурации JPA.

[к оглавлению](#JPA)

## Типы связей между _Entity_
Все типы связей между _Entity_ в JPA можно поделить на `2` большие группы :
+ _Bidirectional_ - ссылка на связанную `Entity` находится в обеих из них, при этом одна из них является владельцем отношения (это важно при каскадном удалении, при этом при удалении владельца будет удален и второй участник связи, но не наоброот).
+ _Unidirectional_ - ссылка на связанную `Entity` находится только в одной из них, то есть вторая сущность о первой не знает.

Также можно выделить `4` основных вида связей :
1. _One-to-One_ - связь один-к-одному, когда один объект `Entity` может быть связан не более чем с одним объектом другого `Entity`.
2. _One-to-Many_ - связь один-ко-многим, когда в одном объекте `Entity` содержится коллекция объектов другого `Entity`.
3. _Many-to-One_ - связь многие-к-одному, когда один объект `Entity` содержится в коллекции объекта другого `Entity`. Обратная для _One-to-Many_.
4. _Many-to-Many_ - связь многие-ко-многим, когда один объект `Entity` содержит коллекцию объектов другого `Entity`, и наоборот.

Таким образом, если совместить эти две классификации, выйдет, то всего возможных типов связей между _Entity_ в JPA всего `8` штук.

[к оглавлению](#JPA)

## Типы _Fetch_ стратегии
В _JPA_ описаны `2` типа fetch стратегии :
+ _EAGER_ - данные поля будут загружены сразу. Данная стратегия по умолчанию используется в отношениях :
    + _One-to-One_
    + _Many-to-One_
+ _LAZY_ - данные поля будут загружены только в момент первого обращения к ним. Данная стратегия используется по умолчанию в отношениях :
    + _One-to-Many_
    + _Many-to-Many_
    
[к оглавлению](#JPA)

## Mapped Superclass
+ _Mapped Superclass_ - это класс, от которого наследуются _Entity_, он может содержать JPA аннотации, но однако сам такой класс не является _Entity_ и ему не обязательно выполнять требования для _Entity_ (Например, он может не содержать первичный ключ).
+ _Mapped Superclass_ не может использоваться в операциях _EntityManager_ или _Query_.
+ _Mapped Superclass_ должен быть отмечен специальной аннотацией `@MappedSuperclass` или описан в xml-файле.

[к оглавлению](#JPA)

## Стратегии наследования маппинга в JPA
Стратегии наследования маппинга - это как JPA будет работать с классами-наследниками _Entity_.

Стратегий наследования маппинга в JPA есть `3` :
1. __Single table per hierarchy__. В этой стратегии `Entity` вместе со своими наследниками записываются в одну таблицу, а для различия типов вводиться специальная колонка `discriminator column`. Минусом такой стратегии является то, что в таблице будут присутствовать колонки абсолютно для каждого наследника, а значит, будет много пустых значений.
2. __Joined subclass strategy__. В этой стратегии все общие поля предка сохраняются в одной таблице, и для каждого наследника создается своя таблица с уникальными для него полями. Минусом этой стратегии является потеря производительности для любых операций за счет объединения таблиц (`JOIN`).
3. __Table per concrete class strategy__. В этой стратегии каждый отдельный класс-наследник имеет свою отдельную таблицу, то есть, данные записываются так, как будто суперкласса нету вовсе. Минусом этой стратегии является поддержка полиморизма и то, что для выборки значений всех классов иерархии потребуется много SQL-запросов.

[к оглавлению](#JPA)

## `EntityManager`
+ `EntityManager` - это интерфейс, который описывает API для всех основных операций над `Entity` и другими сущностями JPA.
+ По сути `EntityManager` является главным API для работы с JPA.

[к оглавлению](#JPA)

## Методы `EntityManager`
Основные операции `EntityManager` делятся на `5` групп :
1. Операции над `Entity` :
    + `persist` - добавление _Entity_ под управление JPA
    + `merge` - обновление
    + `remove` - удаление
    + `refresh` - обновление данных
    + `detach` - удаление _Entity_ из управления JPA
    + `lock` - блокирование _Entity_ для изменений в других `thread`
2. Получение данных :
    + `find` - поиск и получение _Entity_
    + `createQuery` - создание JPQL-запроса
    + `createNamedQuery` - создание переиспользуемого JQPL-запроса
    + `createNativeQuery` - создание SQL-запроса
    + `contains` - проверка, хранится ли _Entity_ в JPA
    + `createNamedStoredProcedureQuery` - создание именнованого запроса-хранимой процедуры
    + `createStoredProcedureQuery` - создание запроса-хранимой процедуры
3. Получение других сущностей JPA :
    + `getTransaction` - получение транзакции
    + `getEntityManagerFactory` - получение фабрики, из которой можно достать `EntityManager`
    + `getCriteriaBuilder` - получение билдера для построения критериев поиска
    + `getMetamodel` - получение метаданных о каком-либо _Entity_
    + `getDelegate` - возвращает провайдер для `EntityManager`
4. Работа с `EntityGraph` :
    + `createEntityGraph` - создание `EntityGraph`
    + `getEntityGraph` - получение `EntityGraph`
5. Общие операции над `EntityManager` или всеми _Entities_ :
    + `close` - закрытие `EntityManager`
    + `isOpen` - проверка, открыт ли `EntityManager`
    + `getProperties` - возвращает свойства `EntityManager`
    + `setProperty` - задает свойство `EntityManager`
    + `clear` - очищает `persistence context`
 
[к оглавлению](#JPA)

## Состояния _Entity_ и переходы между ними
![alt text](https://3.bp.blogspot.com/-oI9s7pkkXJs/Tnh0grho31I/AAAAAAAABFQ/-OIkW8ia5UQ/s1600/entity+states.png)

Как видим, у каждой _Entity_ есть `4` состояния :
1. _new_ - объект только создан и еще не управляется JPA и не сохранен в БД. Отсюда следует, что у него нет первичного ключа.
2. _managed_ - объект управляется _JPA_, у него есть первичный ключ.
3. _detached_ - объект уже не управляется _JPA_.
4. _removed_ - объект управляется с помощью _JPA_, но будет удален после `commit`-а транзакции.

Для перехода между состояниями _Entity_ используются следующие операции :
1. `persist (Object entity) -> Object` :
    + _new_ >> _managed_
    + _removed_ => _managed_
2. `merge (Object entity) -> Object` :
    + _new_ => _managed_
    + _detached_ => _managed_
3. `remove (Object entity) -> void` :
    + _managed_ => _removed_
4. `refresh (Object entity) -> void ` :
    + _managed_ => _managed_
5. `detach (Object entity) -> void` :
    + _managed_ => _detached_
6. `find (Class entityClass, Object key) -> Object` :
    + _database_ => _managed_
7. `createQuery (String query).getResultList() -> List` :
    + _database_ => _managed_
7. `close() -> void` - меняет состояние всех _managed_ объектов на _detached_ :
    + _managed_ => _detached_
8. `clear() -> void` - меняет состояние всех _managed_ объектов на _detached_ :
    + _managed_ => _detached_
9. `flush() -> void` - сохраняет изменение во всех _managed_ объектах в БД, а также удаляет все _removed_ объекты :
    + _managed_ => _database_
    + _removed_ => _database_
    
[к оглавлению](#JPA)

## Операция `persist` на _Entity_ в разных состояниях
1. Если статус _new_, то он меняется на _managed_, и объект будет сохранен в БД при `commit` - е транзакции или в результате операции `flush`.
2. Если статус уже _managed_, то операция игнорируется, однако зависимые _Entity_ могут поменять статус на _managed_, если активен `CascadeType.PERSIST` или `CascadeType.ALL`.
3. Если статус _detached_, то будет выкинут `exception` сразу или на этапе коммита транзакции.
4. Если статус _removed_, то он поменяется на _managed_.

[к оглавлению](#JPA)

## Операция `merge` на _Entity_ в разных состояниях
1. Если статус _new_, то будет создана новая _Entity_ со статусом _managed_, в которую скопируются данные прошлого объекта.
2. Если статус _managed_, то операция будет проигнорирована, но операция `merge` может сработать на каскадно зависимые _Entity_, если их статус не _managed_.
3. Если статус _detached_, то данные будут скопированы в существующую _managed_ _Entity_ с тем же первичным ключом, либо будет создан новая _Entity_ со статусом _managed_, в которую скопируются данные.
4. Если статус _removed_, то будет выкинут `exception` сразу или на этапе коммита транзакции.

[к оглавлению](#JPA)

## Операция `remove` на _Entity_ в разных состояниях
1. Если статус _new_, операция игнорируется, однако зависимые каскадные _Entity_ могут стать _removed_, если до этого были _managed_.
2. Если статус _managed_, то статус поменяется на _removed_ и объект будет удален из базы данных вместе со своими каскадными зависимостями при `commit` - е транзакции.
3. Если статус _detached_, то будет выкинут `exception` сразу или на этапе коммита транзакции.
4. Если статус _removed_, то операция игнорируется.

[к оглавлению](#JPA)

## Операция `detach` на _Entity_ в разных состояниях
1. Если статус _new_, то операция проигнорируется.
2. Если статус _managed_, то статус _Entity_ и всех каскадно зависимых от нее объектов поменяется на _detached_.
3. Если статус _detached_, то операция проигнорируется.
4. Если статус _removed_, то статус _Entity_ и всех каскадно зависимых от нее объектов поменяется на _detached_. 
    
[к оглавлению](#JPA)
    
## Операция `refresh` на _Entity_ в разных состояниях
1. Если статус _new_, будет выкинут `exception`.
2. Если статус _managed_, то в результате операции будут восстановлены все изменения из базы данных данного _Entity_, и так же произойдет `refresh` всех каскадно зависимых объектов.
3. Если статус _detached_, будет выкинут `exception`.
4. Если статус _removed_, будет выкинут `exception`.

[к оглавлению](#JPA)
    
## Аннотации JPA    
Все нижеперечисленные аннотации находятся в пакете `javax.persistence` :
+ __Базовые аннотации__ :
    + `@Entity` - указывает, что данный класс является сущностью.
    ```java
    @Entity
    public class Cat implements Serializable {
    ...
    }
    ```
    + `@Table` - позволяет менять параметры таблицы, связанной с сущностью. Например, тут можно например задать уникальные столбцы таблицы или ее имя.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
    ...
    }
    ```
    + `@Column` - позволяет менять параметры колонки, например, имя.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
     
      @Column(name = "catName")
      private String name;
       
    ...
    }
    ```
    + `@Id` - указывает что данное поле является первичным ключом.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
     
      @Id
      @Column(name = "id")
      private int id;
       
    ...
    }
    ```
    + `@GeneratedValue` - указывает, что даннное свойство будет создаваться автоматически согласно указанной стратегии.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
     
      @Id
      @GeneratedValue(strategy = IDENTITY) //AUTO, SEQUENCE, TABLE
      @Column(name = "id")
      private int id;
       
    ...
    }
    ```
    + `@Version` - помогает управлять версией в записи сущности. При изменении записи увеличится на `1`.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
     
      @Version
      @Column(name = "version")
      private int version;
       
    ...
    }
    ```
    + `@OrderBy` - позволяет указать сортировку поля-коллекции.
    ```java
   @Entity
   @Table(name = "cat_table")
   public class Cat implements Serializable {
    
    @OrderBy("firstName asc")
    private Set catsSet; 
   ...
   }
    ```
    + `@Transient` - указывает, что поле не нужно сохранять в БД. `static` и `final` поля всегда _transient_.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
     
     @Transient
      public boolean isNew() {
          return id == null;
       }
     
    ...
    }
    ```
    + `@Lob` - указание на большие объекты.
    + `@PersistenceContext` - указывает на зависимость `EntityManager` в контейнере, помогает получить его _instance_.
    ```java
    @Service("jpaCatService")
    @Repository
    @Transactional
    public class CatServiceImpl implements CatService {
     
    	@PersistenceContext
    	private EntityManager em;
    ...
    }
    ```
    + `@Temporal` - указываем, чтобы обозначить, что работам с `java.util.Date` или `java.util.Calendar`. Нужно потому, что в БД время может сохраняться как `sql.Date`.
    ```java
    public class Cat implements Serializable {
     
      private java.util.Date birthDate; //in DB schema uses sql.Date in column BIRTH_DATE. 
     
      @Temporal(TemporalType.DATE)
      @Column(name = "BIRTH_DATE")
      public Date getBirthDate() {
    	  return this.birthDate;
      }
    ...
    }
    ```
    + `@Embeddable` и `@Embedded` - первая из них определяет класс, экземпляр которого хранится как неотъемлемая часть `Entity`. Вторая - для того чтобы указать, что поле является таким объектом.
    ```java
   @Embeddable 
    public class Address {
        protected String street;
        protected String city;
        protected String state;
  
        @Embedded 
        protected Zipcode zipcode;
    }
    
    @Embeddable 
    public class Zipcode {
        protected String zip;
        protected String plusFour;
    }
    ```
  
+ __Аннотации для связей__ :
    + `@OneToOne` - применяется для обозначения связи один-к-одному. Имеет такие параметры (самые интересные) :
        + `orphanRemoval` - позволяет удалить объекты-сироты.
        + `mappedBy` - обратная связь для `@JoinColumn`. Внутри пишется название поля в связанной сущности, через которое идет связка с этой.
        + `cascade` - свойства распространения действий с сущностью на связанные с ней сущности.
    ```java
    @Entity
    @Table(name = "contactDetail")
    public class ContactDetail implements Serializable {
     
      @Id
      @Column(name = "id")
      @GeneratedValue
      private int id;
       
      @OneToOne
      @MapsId
      @JoinColumn(name = "contactId")
      private Contact contact;
       
      ...
    }
     
    @Entity
    @Table(name = "contact")
    public class Contact implements Serializable {
     
      @Id
      @Column(name = "ID")
      @GeneratedValue
      private Integer id;
     
      @OneToOne(mappedBy = "contact", cascade = CascadeType.ALL)
      private ContactDetail contactDetail;
     
      ....
    }
    ```
    + `@ManyToOne` - указывает на связь многие-к-одному.
    ```java
    @Entity
    @Table(name = "cat_table")
    public class Cat implements Serializable {
    ...
    }
    ```
    + `@OneToMany` - указывает на связь один-ко-многим.
    ```java
    @Entity
    @Table(name = "contact")
    public class Contact implements Serializable {
     
    private Set<ContactTelDetail> contactTelDetails = new HashSet<ContactTelDetail>();
    //...
    	@OneToMany(mappedBy = "contact", cascade=CascadeType.ALL, orphanRemoval=true)
    	public Set<ContactTelDetail> getContactTelDetails() {
    		return this.contactTelDetails;
    	}
    ....
    }
    @Entity
    @Table(name = "contact_tel_detail")
    public class ContactTelDetail implements Serializable {
     
    private Contact contact;
    //...
            @ManyToOne
            @JoinColumn(name = "CONTACT_ID")
            public Contact getContact() {
    	        return this.contact;
    	}
    }
    ```
    + `@ManyToMany` - указывает на связь многие-ко-многим
    ```java
    @Entity
    @Table(name = "contact")
    public class Contact implements Serializable {
     
    private Set<Hobby> hobbies = new HashSet<Hobby>();
    //...
    	@ManyToMany
    	@JoinTable(name = "contact_hobby_detail", 
    	      joinColumns = @JoinColumn(name = "CONTACT_ID"), 
    	      inverseJoinColumns = @JoinColumn(name = "HOBBY_ID"))
    	public Set<Hobby> getHobbies() {
    		return this.hobbies;
    	}
    ....
    }
     
    @Entity
    @Table(name = "hobby")
    public class Hobby implements Serializable {
     
    private Set<Contact> contacts = new HashSet<Contact>();
    //...
     
           @ManyToMany
           @JoinTable(name = "contact_hobby_detail", 
    	      joinColumns = @JoinColumn(name = "HOBBY_ID"), 
    	      inverseJoinColumns = @JoinColumn(name = "CONTACT_ID"))
    	public Set<Contact> getContacts() {
    		return this.contacts;
    	}
    }
    ```
    + `@PrimaryKeyJoinColumn` - главный ключ для ассоциированной сущности с таким же ключом.
    + `@JoinColumn` - применяется для указание колонки, ссылающейся на внешний ключ другой `Entity`.
    ```java
    @Entity
    public class Troop {
        @OneToMany(mappedBy="troop")
        public Set<Soldier> getSoldiers() {
        ...
    }
     
    @Entity
    public class Soldier {
        @ManyToOne
        @JoinColumn(name="troop_fk")
        public Troop getTroop() {
        ...
    }
    ```
    + `@JoinTable` - указывает на связь с помощью промежуточной таблицы.
    + `@MapsId` - связывает поле с первичным ключом в другой `Entity`. Работает c `@Id`.
    ```java
    @Entity
    @Table(name="student")
    public class Student implements Serializable {
    	
    	@Id
    	@Column(name="sl_id")
    	private int slNum;
    	
    	@MapsId
    	@OneToOne
    	@JoinColumn(name = "std_id")
    	private Person student;
     
    	@Column(name="location")
    	private String location;
    	public Student(int slNum,Person student, String location){
    		this.slNum=slNum;
    		this.student=student;
    		this.location=location;
    	}
     
     
    @Entity
    @Table(name="person")
    public class Person implements Serializable {
    	
    	@Id
    	@Column(name="p_id")
    	private int id;
     
            @Column(name="first_name")
    	private String firstName;
    	
    	@Column(name="last_name")
    	private String lastName;
    ..
    }
    ```
+ __Аннотации наследования__ :
    + `@Inheritance` - аннотация, позволяющая задать параметры наследования, такие как стратегия, `discriminatorValue` и т.д.
    + `@DiscriminatorColumn` - позволяет задать название колонки дескриминатора (Для стратегии наследования с одной таблицей на все сущности иерархии).
    + `@DiscriminatorValue` - позволяет задать значение дескриминатора для данной сущности (Для стратегии наследования с одной таблицей для всех сущностей иерархии).
    ```java
    @Entity
    @Table(name="EJB_PROJECT")
    @Inheritance(strategy=JOINED)
    @DiscriminatorColumn(name="PROJ_TYPE")
    @DiscriminatorValue("P")
    public class Project implements Serializable {
    ...
        @Id
        @Column(name="PROJECT_ID", primaryKey=true)
        public Integer getId() {
            return id;
        }
    ...
    }
    ```
+ __Аннотации запросов__ :
    + `@NamedQueries` - внутри нее указывается список именованных запросов.
    + `@NamedQuery` - имя именованного запроса и сам запрос.
    + `@SqlResultSetMapping` - указывается, куда будет собран результат.
    + `@EntityResult` - указание сущности, в которой будет сконструирован результат.
    
[к оглавлению](#JPA)

## Cascade Types в JPA
В JPA есть `6` видов Cascade типов. Все они представлены в `javax.persistence.CascadeType` :
+ `ALL` - распространяет все виды операций на чайлдов.
+ `PERSIST` - распространяет операцию `persist` на чайлдов.
+ `MERGE` - распространяет операцию `merge` на чайлдов.
+ `REMOVE` - распространяет операцию `remove` на чайлдов.
+ `REFRESH` - распространяет операцию `refresh` на чайлдов.
+ `DETACH` - распространяет операцию `detach` на чайлдов.

Пример присвоение `CascadeType` в `parent` :
```java
@Entity
class Employee {

    @OneToOne(cascade=CascadeType.REMOVE)
    private Address address;
}
```

[к оглавлению](#JPA)

## `orphanRemoval`
_Orphan removal_ помогает нам в удалении объектов, на которых не осталось ссылающихся объектов в БД и _persistent_ контексте. 

Пример : 
```java
@Entity
class Employee {

    @OneToOne(orphanRemoval=true)
    private Address address;
}
```

[к оглавлению](#JPA)

## В чем отличие между `cascade=CascadeType.REMOVE` и `orphanRemoval=true`?
+ Разница в том, что `orphanRemoval` - это более агрессивный способ удаления зависимых объектов.
+ Все, что делает `CascadeType.REMOVE` - это просто каскадирует удаление _parent_ объекта на _child_ объекты. 
+ `orphanRemoval` же удаляет объект, как только на него не осталось ссылок из других объектов. 
+ Исходя из пунктов выше, в ситуации, когда мы в `parent` удалим ссылку на `child1`, или заменим ее на ссылку на другого `child2`, то в случае `CascadeType.REMOVE` с `child1` ничего не произойдет, а в случае с `orphanRemoval` он сразу же удалится.

[к оглавлению](#JPA)

## Callback методы
+ _Callback методы_ служат для вызова при определенных событиях в жизненном цикле `Entity`.
+ _Callback методы_ могут быть добавлены к :
    + _Entity_ классу
    + Mapped superclass - у
    + Callback Listener классу, заданному аннотацией `@EntityListeners`.
+ Существует `7` callback аннотаций, которые навешиваются над callback методами :
    + `@PrePersist`
    + `@PostPersist`
    + `@PreRemove`
    + `@PostRemove`
    + `@PreUpdate`
    + `@PostUpdate`
    + `@PostLoad`
    
[к оглавлению](#JPA)
