fetch - получение очередной строки результата запроса
    mixed PDOStatement::fetch([int fetch_style])

Описание
========

Метод возвращает очередную запись из результирующего набора запроса PDOStatement в указанном виде.

Аргументы
=========

* fetch_style - формат представления данных:
    * PDO::FETCH_ASSOC - возвращает массив, индексированный именами столбцов результирующего набора;
    * PDO::FETCH_BOTH (по умолчанию) - возвращает массив, индексированный именами столбцов результирующего набора, а также их номерами (начиная с 0);
    * PDO::FETCH_NUM - возвращает массив, индексированный номерами столбцов (начиная с 0);
    * PDO::FETCH_OBJ - создает анонимный объект со свойствами, соответствующими именам столбцов результирующего набора.

Возвращаемое значение
=====================

Очередная запись результирующего набора в заданном формате или False, если записей для выборки больше нет.

Пример использования
====================

Выборка записей результирующего набора:

    $db = new PDO('mysql:dbname=test;host=localhost', 'root', '123');
    $result = $db->query('SELECT * FROM myTable');
    while($row = $result->fetch(PDO::FETCH_NUM)){
      echo $row[0] . "\t" . $row[1];
    }
