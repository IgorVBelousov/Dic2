printf - форматированный вывод в поток
    printf(fh, format, list)

Описание
========

Функция пытается записать в поток форматированную строку.

Аргументы
=========

* fh - целевой файловый дескриптор;
* format - формат выходной строки. В данной строке могут быть использованы следующие спецсимволы:
** %s - место подстановки строки;
** %d - место подстановки числа.
* list - необязательные, динамические переменные, подставляемые в выходную строку в порядке их следования.

Пример использования
====================

Запись форматированной строки:

    printf(STDOUT, 'Hello %s', $username);