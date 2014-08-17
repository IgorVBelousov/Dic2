basename - получение имени файла из пути
    string basename(string path)

Описание
========

Функция возвращает имя файла из указанного пути.

Аргументы
=========

* path - исходный путь.

Возвращаемое значение
=====================

Имя файла.

Пример использования
====================

Получение имени файла:

    $path = "/home/httpd/html/index.php";
    echo basename($path); // index.php