# Домашнее задание к занятию «Базы данных, их типы» - Кощеев Иван
### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.


1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.


1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.


1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.


*Приведите ответ в свободной форме.*

### Ответ:

<details>

### 1.1
Тип СУБД: Реляционная (например, PostgreSQL, MySQL, Microsoft SQL Server).
###### Обоснование:
1) Реляционные СУБД обеспечивают целостность данных через ACID-транзакции, что критично для финансовых операций.
2) Чёткая структура (таблицы, схемы) подходит для сложных запросов, агрегаций и аналитики.
3) Поддержка SQL упрощает формирование отчётов и интеграцию с BI-инструментами (Power BI, Tableau).
4) Возможность использовать OLAP-расширения (например, столбчатые хранилища) для прогнозирования и анализа больших объёмов данных.
 
### 1.2 
Для лендингов: Документная NoSQL (например, MongoDB, Couchbase).
Для CRM: Документная или гибридная СУБД (MongoDB, Cassandra).

###### Обоснование:

###### Лендинги:
1) Каждый проект может иметь уникальную структуру данных. Документные СУБД позволяют хранить данные в формате JSON/BSON без жёсткой схемы.
2) Высокая скорость записи/чтения, что важно для обработки лидов в реальном времени.

###### CRM:

1) Гибкость для хранения разнородных данных (контакты, история взаимодействий, сделки).
2) Возможность масштабирования горизонтально при росте нагрузки.
3) Если CRM требует сложных связей (например, иерархии клиентов), можно рассмотреть графовую СУБД (Neo4j), но документные чаще используются для баланса гибкости и скорости.

### 1.3 

Реляционная (например, PostgreSQL) или иерархическая (например, XML/JSON-хранилища в документной СУБД).
###### Обоснование:
1) Если данные имеют строгую иерархию (например, разделы → подразделы → документы), подойдёт реляционная СУБД с поддержкой древовидных структур (через adjacency list или nested sets).
2) Альтернатива: документная СУБД (MongoDB) для хранения вложенных структур (например, разделов с подразделами внутри документа).
3) Простота администрирования и интеграции с корпоративными системами (например, Confluence или SharePoint, которые часто используют реляционные БД на бэкенде).

### 1.4

Тип СУБД: Графовая (например, Neo4j, Amazon Neptune).
###### Обоснование:
1) Графовые СУБД оптимальны для работы со связями (например, поиск кратчайшего пути, анализ зависимостей между точками доставки).
2) Позволяют моделировать сложные сети (объекты, курьеры, маршруты) и решать задачи оптимизации в реальном времени.
3) Высокая производительность для запросов типа "найти все маршруты между A и B с учётом пробок" или "распределить курьеров по геозонам".

</details>
---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

*Приведите ответ в свободной форме.*

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 


*Приведите ответ в свободной форме.*

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

*Приведите ответ в свободной форме.*

---
