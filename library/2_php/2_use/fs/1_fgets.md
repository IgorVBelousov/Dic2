fgets - чтение строки из файла
    bool|string fgets(resource handle, int length)

Описание
========

Функция считывает указанное число байт из файла.

Аргументы
=========

* handle - целевой файловый дескриптор;
* length - число считываемых байт.

Возвращаемое значение
=====================

Считанная строка указанной длины или False в случае возникновения ошибки.