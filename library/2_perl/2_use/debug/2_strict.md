strict - строгий синтаксис
Прагма strict
=============

Прагма strict делает синтаксис Perl строже, что позволяет избежать многих ошибок программной архитектуры. Данная прагма различает три основные области воздействия:

* `strict refs` - ограничения на символические ссылки. Все виды символических ссылок будут запрещены в Perl;
* `strict vars` - ограничения на объявления переменных. Любое использование не объявленной ранее переменной будет приводить к ошибке;
* `strict subs` - ограничения на выполнение подпрограмм. Ссылаться на подпрограммы можно только через строковую константу или взятие адреса.

Использование strict без аргумента включает все возможные ограничения.