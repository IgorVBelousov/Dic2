array_unshift - добавление элемента в начало массива
    int array_unshift(array &arr, mixed var)

Описание
========

Функция добавляет элемент в начало массива.

Аргументы
=========

* arr - целевой массив;
* var - добавляемое значение.

Возвращаемое значение
=====================

Функция возвращает новое число элементов в целевом массиве.

Пример использования
====================

Добавление элемента в начало массива:

    $arr = [1, 2, 3];
    echo array_unshift($arr, 0); // 4
    print_r($arr); // 0, 1, 2, 3
