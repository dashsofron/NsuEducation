***Руководство по второй лабораторной работе***
===============================================
1. Задание
------------
В данной лабораторной работе от вас требуется вызуализировать работу std::sort.
Делать это необходимо в 2 этапа:  

**I. Вывод в консоль.**   
Для этого определяете методы класса **Elem** (main/element.h), чтобы во время сортировки в консоль выводилась информация о том, что происходит.    
В качестве подсказки - класс **Elem** хранит своими полями свой индекс в контейнере и целочисленное значение, по которому объекты этого класса и должны сравниваться.   
Так же в класссе **Elem** уже определен int operator() const.

**II. Вывод на экран.**     
Теперь вам необходимо воспользоваться классом **Visualizer**, чтобы воспроизвести действия std::sort графически.  
В файле graphics/command.h определен абстрактный базовый класс **Command**. Вы должны в наследниках реализовать его метод execute.   
В качесте аргументов он принимает вектор, сортировку которого и будет визуализировать и массив цветов, которыми будут помечены элементы вектора на экране.   
Вы должны определить команды, и, в зависимости от того, что они делают, выполнить какие-либо манипуляции с переданными аргументами.  
  

Добавьте в вызов этих комманд в методах класса **Elem**:
```cpp
  Visualizer::getInstance().pushCommand(new Comparison_Greater(/* args */));
```


После std::sort:  
```cpp
  Visualizer::getInstance().draw();
```

**Подведя итог, в ваших классах-наследниках Command должно храниться достаточно информации, чтобы при вызове execute вы могли проделать необходимые дейстия.**

**Если все выполнено верно, вы должны увидеть что-то похожее:**  
![Img](https://bitbucket.org/Nikan1234pro/pictures/raw/master/sort.gif)
