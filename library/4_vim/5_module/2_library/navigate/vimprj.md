vimprj - конфигурация проектов
Описание
========

Плагин vimprj позволяет конфигурировать проекты с помощью VimScript.

Установка
=========

Для установки плагина необходимо:

1. Установить плагин [DfrankUtil](http://www.vim.org/scripts/script.php?script_id=3884) от которого зависит данный плагин;
1. Скачать архив плагина по адресу <http://www.vim.org/scripts/script.php?script_id=3872>
2. Установить плагин согласно инструкциям по установке.

Использование
=============

Для того, чтобы сконфигурировать конкретный проект с помощью данного плагина, достаточно создать каталог с именем `.vimprj` в корневом каталоге проекта и поместить в него все необходимые файлы конфигурации на языке VimScript.

Опции и команды
===============

Плагин реализует следующие переменные:

* `$INDEXER_PROJECT_ROOT` - абсолютный адрес корневого каталога проекта.
