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

## Задача 5

Получите полную информацию по выполнению запроса выдачи всех пользователей из задачи 4 
(используя директиву EXPLAIN).

Приведите получившийся результат и объясните, что значат полученные значения.

## Задача 6

Создайте бэкап БД test_db и поместите его в volume, предназначенный для бэкапов (см. задачу 1).

Остановите контейнер с PostgreSQL, но не удаляйте volumes.

Поднимите новый пустой контейнер с PostgreSQL.

Восстановите БД test_db в новом контейнере.

Приведите список операций, который вы применяли для бэкапа данных и восстановления. 

---

### Как cдавать задание

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---

