Настройки git
Игнорирование файлов
=====================

Если необходимо определить некоторые файлы или каталоги в репозитории, которые не должны учитываться Git, необходимо создать файл с именем .gitignore в корневом каталоге репозитория. Данный файл может содержать следующие команды:

* `#` - комментарий. Все от данного символа до конца строки не учитывается;
* glob-шаблоны - используются для определения имен игнорируемых файлов;
* <каталог>/ - указание на "каталог". Весь каталог будет проигнорирован;
* !<команда> - инверсия "команды", все затрагиваемые ей файлы и каталоги не будут проигнорированы.
