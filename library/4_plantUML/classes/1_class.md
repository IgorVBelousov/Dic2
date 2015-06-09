Классы, методы и свойства
Описание класса
===============

Для описания класса с помощью PlantUML используется следующая конструкция:

    class имя{
        тело
    }

Здесь в качестве "имени" класса может быть указана любая последовательность символов. "Тело" класса заполняется свойствами и методами.

Класс может содержать стереотип, который указывается с помощью следующей записи:

    class имя << стереотип >> {
        тело
    }

Класс может содержать описание, которое указывается с помощью следующей записи:

    class имя < описание > {
        тело
    }

Помимо класса, могут быть указаны следующие типы сущностей:

* Интерфейс (interface);
* Абстрактный класс (abstract class);
* Перечисление (enum);
* Аннотация (annotation).

Ниже приведен пример файла со всеми указанными конструкциями:

    @startuml
    interface List << collection >>{
    }
    abstract class AbstractList{
    }
    List <|-- AbstractList
    class ArrayList < extends AbstractList >{
    }
    AbstractList <|-- ArrayList
    enum TimeUnit {
    }
    annotation SuppressWarnings
    @enduml

В результате компиляции такого файла, будет получена схема, изображенная на рисунке:

![Схема классов PlantUML](storage/imgs/plantUML/classes/class/class.png)

Для указания реализуемых классом интерфейсов можно использовать следующую запись:

    интерфейс ()- класс

Ниже приведен пример файла, описывающего класс, реализующий интерфейс:

    @startuml
    List ()- ArrayList
    @enduml

В результате компиляции такого файла, будет получена схема, изображенная на рисунке:

![Реализация интерфейса](storage/imgs/plantUML/classes/class/implement.png)

Свойства класса
===============

Для описания свойств класса, они перечисляются в теле класса в виде следующей записи:

    видимость модификатор тип имя

* Видимость - уровень доступность свойства. Выделяются следующие основные уровни:
    * `-` - приватный;
    * `#` - защищенный;
    * `~` - пакетная приватность;
    * `+` - открытый.
* Модификатор - дополнительные характеристики свойства, такие как:
    * `{static}` - статичное свойство.
* Тип - тип данных, которые могут храниться в свойстве. Значения здесь зависят от используемого языка программирования, но как правило это один из следующих типов:
    * `int` - целое число;
    * `float` - дробное число;
    * `char` - символ;
    * `str` - строка;
    * `bool` - логический тип.
* Имя - наименование свойства.

Ниже приведен пример объявления класса со свойствами:

    @startuml
    class ArrayList{
      - int index
      + {static} int count
    }
    @enduml

В результате компиляции такого файла, будет получена схема, изображенная на рисунке:

![Свойства класса](storage/imgs/plantUML/classes/class/property.png)

Методы класса
=============

Для описания методов класса, они перечисляются в теле класса в виде следующей записи:

    видимость модификатор тип имя(аргументы)

* Видимость - уровень доступность метода. Выделяются следующие основные уровни:
    * `-` - приватный;
    * `#` - защищенный;
    * `~` - пакетная приватность;
    * `+` - открытый.
* Модификатор - дополнительные характеристики метода, такие как:
    * `{static}` - статичный метод;
    * `{abstract}` - абстрактный метод;
* Тип - тип данных, который возвращается из метода после его вызова. Значения здесь зависят от используемого языка программирования, но как правило это один из следующих типов:
    * `int` - целое число;
    * `float` - дробное число;
    * `char` - символ;
    * `str` - строка;
    * `bool` - логический тип.
* Имя - наименование метода;
* Аргументы - перечисленные через запятую имена и типы аргументов, которые принимает метод.

Ниже приведен пример объявления класса с методами:


В результате компиляции такого файла, будет получена схема, изображенная на рисунке:

![Методы класса](storage/imgs/plantUML/classes/class/method.png)

Управление отображением тела класса
===================================

Группировка членов класса
-------------------------

По умолчанию класс UML схемы отображается в виде прямоугольника, разделенного на три секции, первая из которых содержит имя класса, вторая свойства, а третья методы. Вне зависимость от того, как будут перечислены свойства и методы в теле класса, они будут сгруппированы в этих секциях последовательно. Это поведение можно изменить, указав в теле класса следующие конструкции:

* `..` - пунктирный разделитель;
* `==` - двойной разделитель;
* `__` - жирная линия;
* `--` - линия.

Каждый разделитель может содержать краткое описание, которое записывается между двумя маркерами разделителя:

    @startuml
    class ArrayList{
      .. Private ..
      - int index
      -- Public --
      + {static} int count
      == Abstract ==
      + {abstract} int count()
      __ Public __
      + str get(int index)
    }
    @enduml

В результате компиляции такого файла, будет получена схема, изображенная на рисунке:

![Группы](storage/imgs/plantUML/classes/class/group.png)

Модификаторы видимости
----------------------

По умолчанию модификаторы видимости членов класса отображаются в виде небольших маркеров. Для отмены этого поведения, достаточно указать в начале схемы следующую опцию:

    skinparam classAttributeIconSize 0

Данная опция запрещает замену модификатора видимости на графический маркер.