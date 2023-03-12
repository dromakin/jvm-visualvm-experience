Домашнее задание для Netology.ru для курса Java Developer   

# Task Description
Описание и инструкция к выполнению [здесь](https://github.com/netology-code/jd-homeworks/tree/master/jvm/README.md)

# Homework
## Первичный запуск программы
Logs:
```shell
15:15:10: Executing ':JvmExperience.main()'...

> Task :compileJava UP-TO-DATE
> Task :processResources NO-SOURCE
> Task :classes UP-TO-DATE

> Task :JvmExperience.main()
Please open 'ru.netology.JvmExperience' in VisualVm
15:15:40.579416: loading io.vertx
15:15:40.750142: loaded 529 classes
15:15:43.756838: loading io.netty
15:15:44.057186: loaded 2117 classes
15:15:47.062525: loading org.springframework
15:15:47.189801: loaded 869 classes
15:15:50.194936: now see heap
15:15:50.195582: creating 5000000 objects
15:15:50.359110: created
15:15:53.364518: creating 5000000 objects
15:15:53.488807: created
15:15:56.512371: creating 5000000 objects
15:15:56.628771: created

BUILD SUCCESSFUL in 49s
2 actionable tasks: 1 executed, 1 up-to-date
15:16:00: Execution finished ':JvmExperience.main()'.
```

## Рассмотрим поэтапно
```shell
15:15:40.579416: loading io.vertx // загрузка классов vertx в Metaspace.
15:15:40.750142: loaded 529 classes // загружено 529 классов. Значительно увеличился объем Metaspace для хранения этих классов.
```
### Classes
![1.png](docs%2F1.png)

### Heap
![2.png](docs%2F2.png)

### Metaspace
![3.png](docs%2F3.png)


```shell
15:15:43.756838: loading io.netty  // загрузка классов netty в Metaspace.
15:15:44.057186: loaded 2117 classes   // загружено 2117 классов. Значительно увеличился объем Metaspace для хранения этих классов.
```

### Classes
В 43 секунды было 2813 классов, затем стало 4894.

![4.png](docs%2F4.png)
![5.png](docs%2F5.png)

### Heap
А вот используемой Heap Memory стало значительно меньше, значит были удалены неиспользуемые объекты.

![6.png](docs%2F6.png)
![7.png](docs%2F7.png)

### Metaspace
![8.png](docs%2F8.png)
![9.png](docs%2F9.png)


```shell
15:15:47.062525: loading org.springframework   // загрузка классов springframework в Metaspace.
15:15:47.189801: loaded 869 classes    // загружено 869 классов. Увеличился объем Metaspace для хранения этих классов.
```

### Classes
В 46 секунды было 4894 классов, затем стало 5786.

![10.png](docs%2F10.png)

### Heap
А вот используемой Heap Memory стало чуть больше.

![11.png](docs%2F11.png)
![12.png](docs%2F12.png)

### Metaspace
![13.png](docs%2F13.png)


```shell
15:15:50.194936: now see heap
15:15:50.195582: creating 5000000 objects
15:15:50.359110: created
```

### Classes
В Classes загружен 1 класс.

![14.png](docs%2F14.png)
![15.png](docs%2F15.png)

### Heap
Значительно увеличилась Heap, из-за создания большого количества объектов.

![16.png](docs%2F16.png)
![17.png](docs%2F17.png)

### Metaspace
Значительно увеличилось Metaspace, из-за создания большого количества объектов.

![18.png](docs%2F18.png)
![19.png](docs%2F19.png)

```shell
15:15:53.364518: creating 5000000 objects
15:15:53.488807: created
```

### Classes
В Classes изменения отсутствуют.

![20.png](docs%2F20.png)

### Heap
Значительно увеличилась Heap, из-за создания большого количества объектов.

![21.png](docs%2F21.png)

Значительный рост зарезервированного значения Heap, а использованное - снизилось в результате работы Garbage Collector.
![22.png](docs%2F22.png)

### Metaspace
Отсутствие сильных изменений в Metaspace

![23.png](docs%2F23.png)

```shell
15:15:56.512371: creating 5000000 objects
15:15:56.628771: created
```

### Classes
В Classes изменения отсутствуют.

### Heap
Значительно увеличилась Heap, из-за создания большого количества объектов.

Рост зарезервированного значения Heap прекратился.

![24.png](docs%2F24.png)

### Metaspace
Небольшое изменение в Metaspace.

![25.png](docs%2F25.png)
![26.png](docs%2F26.png)


```shell
BUILD SUCCESSFUL in 49s
2 actionable tasks: 1 executed, 1 up-to-date
15:16:00: Execution finished ':JvmExperience.main()'.
```

Изменений не было обнаружено.

![27.png](docs%2F27.png)

![28.png](docs%2F28.png)

![29.png](docs%2F29.png)

Программа завершила работу.
