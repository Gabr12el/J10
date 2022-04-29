# Задание 1. Менеджер Афиши (обязательное к выполнению)

Вам необходимо реализовать менеджер Афиши для фильмов. В качестве объекта фильма можно взять объект строки (название фильма) или создать свой дата-класс.

![image](https://user-images.githubusercontent.com/53707586/152697921-e71d853c-aa2e-482b-be61-39e6c2cfb0b1.png)

В этой задаче не нужно разделять менеджер и репозиторий - все фильмы должны храниться внутри массива в поле самого менеджера. Изначально, сразу после создания, менеджер не должен содержать фильмов. 

Менеджер должен уметь выполнять следующие операции:
1. Добавление нового фильма.
2. Вывод всех фильмов в порядке добавления (`findAll`)
3. Вывод максимум лимит* последних добавленных фильмов в обратном от добавления порядке (`findLast`)

*Сделайте так, чтобы по умолчанию выводилось последние 10 добавленных фильмов, но при создании менеджера можно было указать другое число, чтобы, например, выдавать 5 (а не 10). Т.е. у вас у менеджера должно быть два конструктора: один без параметров, выставляющий лимит менеджера в 10, а другой с параметром, берущий значение лимита для менеджера из параметра конструктора.

Метод получения последних фильмов будет очень похож на тот что был в лекции. Основное отличие будет в том, что вам в его начале надо будет вычислить правильный ожидаемый размер результирующего массива-ответа, а не просто брать длину массива что лежит в поле; сделать это можно заведя целочисленную переменную в которую вы сохраните желаемый размер создаваемого массива, вычислите с помощью условных операторов для неё значение, а затем только создадите массив указав эту переменную как требуемый для него размер, например:

```java
...
  ??? resultLength;
  if ??? {
    resultLength = ???
  } else {
    resultLength = ???
  }
  ??? result = new ???[resultLength];
  for (???) {
    // заполняем result из массива что лежит в поле
    // в обратном порядке
  }
...
```

Не забывайте про использование отладчика для поиска проблем вашей реализации если тесты проходить не будут.

Напишите необходимые, с вашей точки зрения, автотесты на различные состояния менеджера (можно их делать не в одном файле).

Итого: отправьте на проверку ссылку на гитхаб-репозиторий с вашим проектом. 

# Задание 2*. "Менеджер Афиши" (divide and conquer) (НЕобязательная задача)

В первой задаче создайте новую ветку `layers`, в которой разделите менеджера на менеджера и репозиторий.
В репозитории должны быть следующие методы:
1. `findAll` - возвращает массив всех хранящихся в массиве объектов
1. `save` - добавляет объект в массив
1. `findById` - возвращает объект по идентификатору (либо `null`, если такого объекта нет)
1. `removeById` - удаляет объект по идентификатору (если объекта нет, то пусть будет исключение, как на лекции)
1. `removeAll`* - полностью вычищает репозиторий (для удаления всех элементов достаточно в поле `items` положить пустой массив)

Обеспечьте использование менеджером созданного вами репозитория (новых функций в менеджер по сравнению с первым заданием добавлять не нужно). Репозиторий должен быть зависимостью для менеджера (т.е. задаваться через конструктор и храниться в приватном поле).

Напишите 1-2 автотеста, используя Mockito для организации моков репозитория.

Итого: отправьте на проверку ссылку на пулл-реквест ветки `layers` с вашим проектом. 