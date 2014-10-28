Локализация и исправление ошибок
Выполнение скриптов в режиме отладки
====================================

Bash скрипты можно выполнять в режиме отладки. Для применяется два механизма:

* Выполнение скрипта с указанием ключа `-x` интерпретатора (`/bin/sh -x <скрипт>`). В этом случае весь скрипт будет выполнен в режиме отладки;
* Окружение частей скрипта, которые должны выполняться в режиме отладки с помощью команд `set -x` (начать отладку) и `set +x` (завершить отладку). В этом случае отладка будет применена только к этим командам.

Ниже приведен пример скрипта с использованием команды `set`:

    #!/bin/sh
    a=1
    b=2
    set -x # Начало отладки
    echo $(($a + $b))
    set +x # Завершение отладки

Отладка в Bash скриптах осуществляется путем вывода текста команды перед его непосредственным исполнением. Ниже приведен пример выполнения скрипта из предыдущего примера:

    + echo 3
    3
    + set +x

Как видно, текст команды выводится с подстановкой всех значений переменных и выполнением математических операторов.

Если вместо ключа `-x` указать ключ `-vx`, то перед сообщениями отладчика будут выводиться тексты команды в исходном виде. Ниже приведен пример такой отладки:

    echo $(($a + $b))
    + echo 3
    3
    set +vx
    + set +vx