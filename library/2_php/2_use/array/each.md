each - получение текущего элемента массива
    array each(array &arr)

Описание
========

Функция возвращает пару ключ/значение текущего элемента массива и смещает указатель вперед.

Аргументы
=========

* arr - целевой массив.

Возвращаемое значение
=====================

Пара ключ/значение текущего элемента массива.

Пример использования
====================

Получение текущего элемента массива:

    $arr = [1, 2, 3];
    print_r(each($arr)); // [0 => 0, 'key' => 0, 1 => 1, 'value' => 1]