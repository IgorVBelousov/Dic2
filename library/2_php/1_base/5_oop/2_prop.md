Свойства класса
Свойства класса
===============

Свойство класса объявляется с помощью следующей записи:

    <видимость> <модификаторы> $<имя>;

В качестве имени свойства может выступать любая последовательность латинских букв, цифр и знака подчеркивания, начинающаяся с буквы или знака подчеркивания. Принято называть свойства с буквы в нижнем регистре.

В качестве модификатора "видимости" используется одно из следующих значений:

* public - свойство доступно внутри методов любого класса;
* protected - свойство доступно внутри методов класса, в котором оно объявлено, и в его дочерних классах;
* private - свойство доступно внутри методов класса, в котором оно объявлено.

В качестве "модификаторов" могут быть указаны следующие компоненты:

* static - свойство не копируется в объекты класса, а является характеристикой самого класса.

Если свойство имеет значение по умолчанию, оно указывается следующим образом:

    <свойство> = <значение>;

Доступ к свойствам
==================

Для доступа к открытым (public) свойствам объекта через объект, используется запись:

    $<объект>-><свойство>;

Для доступа к статичным (static) свойствам класса, используется запись:

    <класс>::$<свойство>;

Для доступа к свойствам объекта из метода класса, используется запись:

    $this-><свойство>;

Ниже приведен пример объявления класса с двумя свойствами и доступ к ним:

    class People{
      public $name;
      
      public static $count = 0;
      
      public function setName($name){
        $this->name = $name; // Установка значения свойству.
      }
    }
    $obj = new People();
    People::$count++;
    echo $obj->name;

Константы
=========

Для определения константы класса используется запись:

    const <имя> = <значение>;

В качестве имени константы может выступать любая последовательность латинских букв, цифр и знака подчеркивания, начинающаяся с буквы или знака подчеркивания. Принято называть константы используя буквы верхнего регистра.

Для доступа к значению константы используется запись:

    <класс>::<константа>;

Ниже приведен пример класса с определенной константой:

    class My{
      const FOO = 'Hello world';
    }
    echo My::FOO;