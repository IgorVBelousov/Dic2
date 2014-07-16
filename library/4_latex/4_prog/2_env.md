Окружения
Объявление и переопределение окружений
======================================

Для создания нового окружения используется команда:

    \newenvironment{<имя>}{<заменаНачала>}{<заменаКонца>}

Здесь команда `\begin{имя}` будет заменяться на "замену начала", а `\end{имя}` на "замену конца" окружения.

Если необходимо указать обязательные аргументы окружению, используется команда:

    \newenvironment{<имя>}[<числоАргументов>]{<заменаНачала>}{<заменаКонца>}

Доступ к аргументам внутри замещающего текста можно получить по ссылкам вида #1, #2 и так далее до #9.

Если необходимо переопределить уже существующее окружение, используются команды:

    \renewenvironment{<имя>}{<заменаНачала>}{<заменаКонца>}
    \renewenvironment{<имя>}[<числоАргументов>]{<заменаНачала>}{<заменаКонца>}