# Домашнее задание к занятию 2. «SQL»

## Введение

Перед выполнением задания вы можете ознакомиться с 
[дополнительными материалами](https://github.com/netology-code/virt-homeworks/blob/virt-11/additional/README.md).

## Задача 1

Используя Docker, поднимите инстанс PostgreSQL (версию 12) c 2 volume, 
в который будут складываться данные БД и бэкапы.

Приведите получившуюся команду или docker-compose-манифест.

## Ответ 1

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/427a47e0-37da-41a0-9cd3-18c1abe9fb19)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/d157f020-d6fe-4284-a50c-74bc448206e4)


## Задача 2

В БД из задачи 1: 

- создайте пользователя test-admin-user и БД test_db;
- в БД test_db создайте таблицу orders и clients (спeцификация таблиц ниже);
- предоставьте привилегии на все операции пользователю test-admin-user на таблицы БД test_db;
- создайте пользователя test-simple-user;
- предоставьте пользователю test-simple-user права на SELECT/INSERT/UPDATE/DELETE этих таблиц БД test_db.

Таблица orders:

- id (serial primary key);
- наименование (string);
- цена (integer).

Таблица clients:

- id (serial primary key);
- фамилия (string);
- страна проживания (string, index);
- заказ (foreign key orders).

Приведите:

- итоговый список БД после выполнения пунктов выше;
- описание таблиц (describe);
- SQL-запрос для выдачи списка пользователей с правами над таблицами test_db;
- список пользователей с правами над таблицами test_db.

## Ответ 2

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/75ea5b71-b78a-4431-a9ab-422fa837e56c)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/e1d3ac5f-26d8-4901-9631-296ca6d9b3a8)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/2d3c0d75-7f32-4782-a69d-6d831047275c)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/d305fc2c-da6b-4778-9a06-8d96418c9755)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/dadec47e-6043-41b1-83df-9ebc9800850d)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/2f7c62eb-3a27-4d68-9a63-7d8d825ccf21)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/558e9f9d-f157-4bf1-b716-363f7985ef90)


## Задача 3

Используя SQL-синтаксис, наполните таблицы следующими тестовыми данными:

Таблица orders

|Наименование|цена|
|------------|----|
|Шоколад| 10 |
|Принтер| 3000 |
|Книга| 500 |
|Монитор| 7000|
|Гитара| 4000|

Таблица clients

|ФИО|Страна проживания|
|------------|----|
|Иванов Иван Иванович| USA |
|Петров Петр Петрович| Canada |
|Иоганн Себастьян Бах| Japan |
|Ронни Джеймс Дио| Russia|
|Ritchie Blackmore| Russia|

Используя SQL-синтаксис:
- вычислите количество записей для каждой таблицы.

Приведите в ответе:

    - запросы,
    - результаты их выполнения.

## Ответ 3

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/45576775-f057-4f39-83bb-ae67d55a1cff)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/8f060d85-762f-46cf-9272-c4811060f83a)

## Задача 4

Часть пользователей из таблицы clients решили оформить заказы из таблицы orders.

Используя foreign keys, свяжите записи из таблиц, согласно таблице:

|ФИО|Заказ|
|------------|----|
|Иванов Иван Иванович| Книга |
|Петров Петр Петрович| Монитор |
|Иоганн Себастьян Бах| Гитара |

Приведите SQL-запросы для выполнения этих операций.

Приведите SQL-запрос для выдачи всех пользователей, которые совершили заказ, а также вывод этого запроса.
 
Подсказка: используйте директиву `UPDATE`.

## Ответ 4

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/3b4a3df9-6597-4a5c-9239-802e104f9336)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/09673773-8a14-44a4-b3df-e643b6b0ea05)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/46615f3e-c4b0-41f9-8b9d-4f29f75da576)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/0385ca68-e32a-4a80-bc1e-deb5499b8f7e)


## Задача 5

Получите полную информацию по выполнению запроса выдачи всех пользователей из задачи 4 
(используя директиву EXPLAIN).

Приведите получившийся результат и объясните, что значат полученные значения.

## Ответ 5

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/38da7a2b-2381-40bf-a628-db5759126eeb)

Результат выполнения EXPLAIN-запроса будет содержать информацию о выполнении запроса, оптимизации и доступе к данным.
- Хэш-соединение : планировщик запросов определил, что хеш-соединение является наиболее эффективным способом объединения таблиц.
- стоимость : ориентировочная стоимость выполнения запроса. Он состоит из двух частей: стартовая стоимость и общая стоимость. Чем ниже стоимость, тем более эффективным будет запрос.
- rows : примерное количество строк, возвращаемых на каждом этапе плана запроса.
- width : предполагаемая максимальная ширина каждой строки в байтах.
- Hash Cond : условие, используемое для хэш-соединения. В данном случае это сопоставление столбца «id» в таблице «заказы» со столбцом «Заказ» в таблице «клиенты».
- Seq Scan : указывает, что выполняется последовательное сканирование таблиц «заказы» и «клиенты», что означает, что все строки последовательно считываются с диска. Это может быть менее эффективно, чем сканирование индекса при работе с большими таблицами.
- Хэш : этот шаг включает в себя создание хеш-таблицы для операции соединения.
- -> : указывает порядок шагов в плане выполнения.

Выполнено хеш-соединение между таблицами «заказы» и «клиенты», последовательно просматривая обе таблицы. 

## Задача 6

Создайте бэкап БД test_db и поместите его в volume, предназначенный для бэкапов (см. задачу 1).

Остановите контейнер с PostgreSQL, но не удаляйте volumes.

Поднимите новый пустой контейнер с PostgreSQL.

Восстановите БД test_db в новом контейнере.

Приведите список операций, который вы применяли для бэкапа данных и восстановления. 

## Ответ 6

* sudo docker run --rm --volumes-from project_postgres_1 -v project_backup:/backups -e PGPASSWORD=mypassword  postgres:12 pg_dump -h 172.20.0.2 -p 5432 -U test-admin-user -d test_db -f /home/bezumel/project/backups/test_db.backup
* sudo docker stop project_postgres_1
* sudo docker run --name project_postgres_2 -e POSTGRES_PASSWORD=mypassword -v project_data:/var/lib/postgresql/data -d postgres:12
* sudo docker run --rm --volumes-from project_postgres_2 -v project_backup:/backups -e PGPASSWORD=mypassword postgres:12 pg_restore -h 172.20.0.2 -p 5432 -U test-admin-user -d test_db -c /home/bezumel/project/backups/test_db.backup
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/0403cf0c-745f-4044-a124-06d0d6bb59df)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/f1c8c970-c59a-4ddd-acd9-3cf97162e587)

---

### Как cдавать задание

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---

