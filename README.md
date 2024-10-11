# SDB-12-02
Работа с данными (DDL/DML) - Aleksandr Mihajlov SYS34  
  
### Задание 1  
  
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.  
  
1.2. Создайте учётную запись sys_temp.  
  
1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)  
  
1.4. Дайте все права для пользователя sys_temp.  
  
1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)  
  
1.6. Переподключитесь к базе данных от имени sys_temp.  
  
Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
  
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.  
  
1.7. Восстановите дамп в базу данных.  
  
1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)  
  
*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*  
  
*Ответ*  
  
```sql
CREATE USER	'sys_temp'@'localhost' IDENTIFIED BY 'qwerty'

SELECT USER FROM MYSQL.USER

GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost'

FLUSH PRIVILEGES

SHOW GRANTS FOR 'sys_temp'@'localhost'  
  
ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH mysql_native_password BY 'qwerty'

SELECT USER, HOST, PLUGIN FROM mysql.user WHERE PLUGIN='mysql_native_password'

Curl -O https://downloads.mysql.com/docs/sakila-db.zip

CREATE DATABASE Sakila

SHOW DATABASES

SHOW TABLES

USE Sakila

sudo /usr/local/mysql/bin/mysql -u sys_temp -p Sakila < /Users/aleksandrmihajlov/Downloads/sakila-db/sakila-schema.sql

sudo /usr/local/mysql/bin/mysql -u sys_temp -p Sakila < /Users/aleksandrmihajlov/Downloads/sakila-db/sakila-data.sql 
```    

Скриншоты
<details>    

![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.png)  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.1.png)  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.2.png)  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.3.png)  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.4.png)  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.5.png)  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/1.6.png)  
  
### Задание 2  
  
![alt text](https://github.com/AleksandrMihajlov/SDB-12-02/blob/main/2.png)