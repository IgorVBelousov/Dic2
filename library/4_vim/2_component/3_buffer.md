Буферы
Управление буферами
===================

Буфер в Vim это лишь область памяти, хранящая редактируемую с помощью Vim информацию. Каждый буфер может находится в 3 состояниях:

1. active (a) - буфер загружен и имеет связанное с ним окно;
2. hidden (h) - буфер загружен, но не имеет связанного с ним окна;
3. inactive -буфер не загружен и не имеет связанного с ним окна.

Для просмотра списка буферов используется команда `:ls`. Если использовать команду `:ls!`, то будут показаны так же буферы, относящиеся ко всем сессиям Vim.

Для управления буферами используются следующие команды:

* `bad файл` - загрузить "файл" в новый буфер;
* `bd номер` - отчистить и удалить буфер с данным "номером";
* `b номер` - перейти к редактированию буфера с данным "номером";
* `bn` - перейти к редактированию следующего буфера;
* `bp` - перейти к редактированию предыдущего буфера.
