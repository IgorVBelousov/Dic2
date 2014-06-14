print - запись строки в поток
    print(name, string)

Описание
========

Функция пытается записать указанную строку в поток.

Аргументы
=========

* name - скалярная переменная, хранящая ссылку на целевой файловый дескриптор;
* string - записываемая строка.

Пример использования
====================

Запись строки в файл:

    open(my $fh, '>', 'file.txt');
    print($fh, 'Hello world');
    close($fh);