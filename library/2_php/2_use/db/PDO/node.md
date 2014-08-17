PDO
    __construct(string dsn, [string username, [string password, [array driver_options]]])

Описание
========

Класс PDO представляет унифицированный интерфейс доступа к различным СУБД. Объект данного класса представляет открытое соединение с некоторой используемой СУБД.

Аргументы
=========

* dsn - строка, описывающая соединение с СУБД и имеющая следующий формат: <драйвер>:dbname=<имяБД>;host=<хост>:<порт>;
* username - имя пользователя, осуществляющего подключение;
* password - пароль пользователя, осуществляющего подключение;
* driver_options - ассоциативный массив специфичных для данного драйвера настроект подключения.

Пример использования
====================

Подключение к СУБД MySQL:

    $db = new PDO('mysql:dbname=test;host=localhost', 'root', '123');