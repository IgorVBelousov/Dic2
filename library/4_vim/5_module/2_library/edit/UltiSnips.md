UltiSnips
Описание
========

Плагин UltiSnips служит для управления сниппетами в Vim. Сниппет это специальное сокращение, которое заменяется шаблоном данных, которые достаточно немного поправить, а не переписывать весь шаблон.

Сниппеты включают множество полезных функций, таких как автоматический переход к местам редактирования шаблонов, повтор ввода, выполнение стороннего кода во время генерации шаблона и так далее.

Установка
=========

Для установки UltiSnips необходимо:

1. Скачать архив с плагином из репозитория по адресу <https://github.com/SirVer/ultisnips>;
2. Установить плагин согласно инструкция по установке;
3. Создать каталог `$HOME/.vim/UltiSnips` в который будут помещаться файлы сниппетов.

Использование
=============

Файлы сниппетов
---------------

Все сниппеты располагаются в специальных файлах, называемых - файлами снипетов. Эти файлы размещаются в каталоге, определенном переменной `g:UltiSnipsSnippetDirectories`, который в свою очередь располагается по адресу `$HOME/.vim`.

Каждый файл сниппетов имеет имя, соответствующее типу файла, к которому этот сниппет относится. Файлы сниппетов имеют расширение `snippets`. Так, файл сниппетов для языка XML будет иметь имя `xml.snippets`. Существует так же специальный тип файла сниппетов, который называется `all.snippets`, он применяется к файлам всех типов.

Создание сниппета
-----------------

Сниппеты создаются путем использования двух команд: `snippet` и `endsnippet` - между которыми располагается шаблон сниппета.

Команда `snippet` имеет следующую структуру:

    snippet имя ["Описание"] [опции]
    шаблон
    endsnippet

Здесь в качестве "имени" используется такая последовательность символов, которую необходимо будет ввести в документе и нажать `Tab` (по умолчанию для UltiSnips) для вставки шаблона сниппета.

"Описание" сниппета может быть любым и необходимо для того, чтобы пользователь мог различить два сниппета с одинаковым "именем".

В качестве "опций" могут выступать следующие символы:

* `b` - сниппет должен располагаться в начале строки;
* `i` - сниппет должен быть частью слова;

Ниже приведен пример простого сниппета:

    snippet mySnip "Test snippet" b
      This is my snippet!
    endsnippet

Для вставки такого сниппета достаточно ввести следующую сроку: `mySnip` - и нажать клавишу `Tab`. При этом строка `mySnip` будет заменена на строку `This is my snippet!`.

"Шаблон" сниппета представляет собой любые данные со следующими возможными дополнениями:

* `${номер}` - специальная метка, на которой будет помещен курсор после вставки шаблона сниппета. "Номер" метки определяет порядок постановки курсора, сначала на метку с номером 1, затем на метку с номером 2 и так далее. Для задания значения метки по умолчанию, используется запись `${номер:значение}`;
* `$номер` - специальная метка, которая будет содержать те же данные, которые будут введены пользователем в месте метки `${номер}`;
* `${номер/поиск/замена/}` - специальная метка, аналогичная метке `$номер`, но значение которой перед вставкой обрабатываются заданным регулярным выражением;
* `${VISUAL}` - вместо данной метки будет установлен выделенный в Vim блок данных. Для вставки сниппета во время выделения, необходимо выделить текст, нажать `Tab`, затем ввести имя сниппета и вновь нажать `Tab`;
* `` `код` `` - выполняемый сторонний код, содержимое выходного потока которого будет вставлено на его место в шаблоне сниппета. По умолчанию используется код на языке `Bash`, не можно указать другие языки с помощью следующих команд: `!v код VimScript`, `!p код Python`. 

Использование сниппета
----------------------

Для вставки сниппета в документ, достаточно ввести его имя и нажать клавишу `Enter`, при этом взамен имени будет вставлен шаблон снипета, а указатель будет установлен на первый маркер (${1}). Для переключения между маркерами используются клавиши: `C-j` - на следующий маркер; `C-k` - на предыдущий маркер.

Если определено несколько сниппетов с одинаковыми именами, будет открыто окно, в котором будут представлены все эти сниппеты в виде их имен и описания. Пользователю будет необходимо ввести ту цифру, под номером которой представлен в этом окне требуемый сниппет, и нажать `Enter`.

Опции и команды
===============

Плагин использует следующие опции:

* `g:UltiSnipsExpandTrigger` - строка, определяющая какая команда должна использоваться для вставки шаблона сниппета. По умолчанию это `<tab>`;
* `g:UltiSnipsJumpForwardTrigger` - строка, определяющая какая команда должна использоваться для перемещения курсора к следующему маркеру. По умолчанию это `<C-j>`;
* `g:UltiSnipsJumpBackwardTrigger` - строка, определяющая какая команда должна использоваться для перемещения курсора к предыдущему маркеру. По умолчанию это `<C-k>`;

Плагином определены следующие команды:

* `:UltiSnipsEdit` - открыть окно для редактирования файла сниппета, который используется для данного типа файла.