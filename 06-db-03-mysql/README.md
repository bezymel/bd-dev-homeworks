# Домашнее задание к занятию 3. «MySQL»

## Введение

Перед выполнением задания вы можете ознакомиться с 
[дополнительными материалами](https://github.com/netology-code/virt-homeworks/blob/virt-11/additional/README.md).

## Задача 1

Используя Docker, поднимите инстанс MySQL (версию 8). Данные БД сохраните в volume.

Изучите [бэкап БД](https://github.com/netology-code/virt-homeworks/tree/virt-11/06-db-03-mysql/test_data) и 
восстановитесь из него.

Перейдите в управляющую консоль `mysql` внутри контейнера.

Используя команду `\h`, получите список управляющих команд.

Найдите команду для выдачи статуса БД и **приведите в ответе** из её вывода версию сервера БД.

Подключитесь к восстановленной БД и получите список таблиц из этой БД.

**Приведите в ответе** количество записей с `price` > 300.

В следующих заданиях мы будем продолжать работу с этим контейнером.

## Ответ 1

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/2d1ecf73-5045-4a33-b96e-23a8e8d25c10)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/3331ecfd-f507-46bc-b39d-83c24b0af95e)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/0db39658-ee04-4564-90cd-b237cfde0ba1)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/1e5298f3-c615-4461-9d1c-a94ec8a2b7e1)

## Задача 2

Создайте пользователя test в БД c паролем test-pass, используя:

- плагин авторизации mysql_native_password
- срок истечения пароля — 180 дней 
- количество попыток авторизации — 3 
- максимальное количество запросов в час — 100
- аттрибуты пользователя:
    - Фамилия "Pretty"
    - Имя "James".

Предоставьте привелегии пользователю `test` на операции SELECT базы `test_db`.
    
Используя таблицу INFORMATION_SCHEMA.USER_ATTRIBUTES, получите данные по пользователю `test` и 
**приведите в ответе к задаче**.

## Ответ 2

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/b928b0a0-d094-4a0b-b603-4fec532adef1)

## Задача 3

Установите профилирование `SET profiling = 1`.
Изучите вывод профилирования команд `SHOW PROFILES;`.

Исследуйте, какой `engine` используется в таблице БД `orders` и **приведите в ответе**.

Измените `engine` и **приведите время выполнения и запрос на изменения из профайлера в ответе**:
- на `MyISAM`,
- на `InnoDB`.

## Ответ 3

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/769dfce1-c435-4eb9-81a9-8e24fc480c9a)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/13466419-a2b7-4860-9da5-04a7dfb7ed51)

## Задача 4 

Изучите файл `my.cnf` в директории /etc/mysql.

Измените его согласно ТЗ (движок InnoDB):

- скорость IO важнее сохранности данных;
- нужна компрессия таблиц для экономии места на диске;
- размер буффера с незакомиченными транзакциями 1 Мб;
- буффер кеширования 30% от ОЗУ;
- размер файла логов операций 100 Мб.

Приведите в ответе изменённый файл `my.cnf`.

## Ответ 4

![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/46c65c81-904a-41a4-b924-0f2db1809c45)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/c7915d21-0992-4435-acab-44178ad1be0b)
![image](https://github.com/bezymel/bd-dev-homeworks/assets/129361495/1b273d45-01be-4e56-a48b-4d64e6bbea7e)

---

### Как оформить ДЗ

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---

