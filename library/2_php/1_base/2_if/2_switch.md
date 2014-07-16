Структура switch
Структура switch
================

Структура switch позволяет определить ветвь выполнения кода на основании сверки значения переменной с допустимыми значениями. Она имеет следующий вид:

    switch(<переменная>){
      case <значение1>:
        <блок1>;
        break;
      case <значение2>:
        <блок2>;
        break;
      ...
      default:
        <блокИначе>;
    }

Здесь будет выполняться тот блок, номер которого соответствует номеру того значения, которое содержится в "переменной". Если ни одно из значений не соответствует значению переменной, выполняется блок default (если он имеется).

Операторы break используются для остановки выполнения структуры, если их не использовать, будет выполнен подходящий блок кода и все нижеследующие за ним блоки без проверки условия.

Ниже приведен пример использования структуры switch для определения пункта меню:

    switch($time){
      case 'Main':
        echo 'Главная страница';
        break;
      case 'News':
        echo 'Новости';
        break;
      case 'Forum':
      case 'Chat':
        echo 'Форум';
        break;
      default:
        echo 'Выход';
    }