Типизация
Типы данных в PHP
=================

Все данные в PHP делятся на следующие типы:

1. Строки ('Hello world' "Hello world\n") - строки, заключенные в двойные кавычки обрабатываются интерпретатором на предмет раскрытия спецсимволов и переменных в них;
1. Целые числа (1 0 -5) - данные, содержащие только числа и, возможно, знак минуса для обозначения отрицательной величины;
1. Дробные числа (2.7) - данные, содержащие только числа целой и дробной частей, разделенные точкой и, возможно, знак минуса для обозначения отрицательной величины;
1. Логический тип (true 1 '1' false 0 '') - непустая строка, число отличное от нуля и 'true' соответствуют истине, все остальное - ложь;
1. NULL - специальный тип, обозначающий отсутствие данных;
1. Массивы ([1,2,3]) - список данных в виде хэш-таблицы;
1. Объекты - составные данные.

Константы
=========

Для определения константы в PHP используется запись:

    const <имя> = <значение>;

Ниже приведен пример создания константы PI:

    const PI = 3.1415;
    echo PI;