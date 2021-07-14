_Почему понимать декларацию и инициализацию так важно?_   
Заметь вопрос стоит **не в запоминании этих слов, а в понимании этих вещей!**  
Ответ очевиден -   
Потому что понимание декларации и инициализации даёт нам фундамент правильного понимания кода (его образа в голове!)

Java-код можно разделить на:   
1) **Классы** - сущности с полями (они могут быть пустыми, объектами или примитивами) и действиями
2) **Методы** - действия
3) **Переменные** - поля класса или метода (могут быть пустыми, объектами или примитивами) для машины это ячейки в памяти

##### Рассмотрим декларацию классов! Допустим у нас есть программа:
```java
public class Main {

    public static void main(String[] args) {
        System.out.println("Я программа у меня есть чертёж (декларация) машины");
    }

    public static class Car {

        String color; //цвет
        String mark; //марка
        String model; //модель
        String engineSound; //звук двигателя
        int power; //мощность
        int mass; //масса

        /**
         * Конструктор класса Car (он ждёт данные по которым будет строить машину)
         */
        public Car(String color, String mark, String model, String engineSound, int power, int mass) {
            this.color = color;
            this.mark = mark;
            this.model = model;
            this.engineSound = engineSound;
            this.power = power;
            this.mass = mass;
        }
    }
}
```
Для программы не существует ни одной машины (объекта класса `Car`), но программа знает об устройстве машин 
(о самом классе `Car`) или говоря более правильно - класс `Car` декларирован в программе.   

Вот этот участок кода:
```java 
    public static class Car {

        String color; //цвет
        String mark; //марка
        String model; //модель
        String engineSound; //звук двигателя
        int power; //мощность
        int mass; //масса

        /**
         * Конструктор класса Car (он ждёт данные по которым будет строить машину)
         */
        public Car(String color, String mark, String model, String engineSound, int power, int mass) {
            this.color = color;
            this.mark = mark;
            this.model = model;
            this.engineSound = engineSound;
            this.power = power;
            this.mass = mass;
        }
    }
```
является декларацией класса (общим для всех машин чертежом).   
Т.е. да! по сути **сам класс - это декларация**   
Но понять ты должен то, что **чертёж машины, не является самой машиной!**   
Для этого существует инициализация (создание объектов)  

##### Теперь рассмотрим Инициализацию классов (создание объектов):
```java
public class Main {

    public static void main(String[] args) {
        System.out.println("Я программа у меня есть чертёж (декларация) машины");
        Car matiz = new Car("Красный", "Daewoo", "Matiz", "тРтрТртрТ", 55, 800);
        Car mustang = new Car("Жёлтый", "Ford", "Mustang", "ВррРРРР!!!", 500, 2100);
        System.out.println("По чертежам я создала 2 машины");
        System.out.println("Первая машина: " + mustang.mark + " " + mustang.model);
        System.out.println("Вторая машина: " + matiz.mark + " " + matiz.model);
    }

    public static class Car {

        String color; //цвет
        String mark; //марка
        String model; //модель
        String engineSound; //звук двигателя
        int power; //мощность
        int mass; //масса

        /**
         * Конструктор класса Car (он ждёт данные по которым будет строить машину)
         */
        public Car(String color, String mark, String model, String engineSound, int power, int mass) {
            this.color = color;
            this.mark = mark;
            this.model = model;
            this.engineSound = engineSound;
            this.power = power;
            this.mass = mass;
        }
    }
}
```
Теперь программа создала 2 **реально существующих объекта класса `Car`** (2 машины **mustang** и **matiz**), это и есть **инициализация!!!**

Вот этот участок кода:
```java
Car mustang = new Car("Жёлтый", "Ford", "Mustang", 500, 2100);
Car matiz = new Car("Красный", "Daewoo", "Matiz", 55, 800);
```
является **инициализацией объектов класса** `Car`. Вернее тут 2 инициализации для двух объектов.  

Как видишь **для каждого класса может быть только одна декларация.**  
А **количество инициализаций объектов одного и того же класса ограничено только размером оперативной памяти** :)   
Важно понимать, что **декларация без инициализации - возможна, а инициализация без декларации - нет**. Логично :) 
_Ведь нельзя построить машину не имея чертежа. А художник без образа в голове не нарисует картину. И т.п._ 

##### Рассмотрим декларацию методов дополнив нашу программу:
```java
public class Main {

    public static void main(String[] args) {
        System.out.println("Я программа у меня есть чертёж (декларация) машины");
        Car matiz = new Car("Красный", "Daewoo", "Matiz", "тРтрТртрТ", 55, 800);
        Car mustang = new Car("Жёлтый", "Ford", "Mustang", "ВррРРРР!!!", 500, 2100);
        System.out.println("По чертежам я создала 2 машины");
        System.out.println("Первая машина: " + mustang.mark + " " + mustang.model);
        System.out.println("Вторая машина: " + matiz.mark + " " + matiz.model);
        System.out.println("Я программа и я знаю, что машины умеют разгоняться, в зависимости от их массы и мощности, но пока я не разгоняла ни одну машину");
    }

    public static class Car {

        String color; //цвет
        String mark; //марка
        String model; //модель
        String engineSound; //звук двигателя
        int power; //мощность
        int mass; //масса

        /**
         * Конструктор класса Car (он ждёт данные по которым будет строить машину)
         */
        public Car(String color, String mark, String model, String engineSound, int power, int mass) {
            this.color = color;
            this.mark = mark;
            this.model = model;
            this.engineSound = engineSound;
            this.power = power;
            this.mass = mass;
        }

        /**
         * Метод расчета времени разгона до ста.
         * В зависимости от мощности и массы
         */
        public double accelerationToHundredTime() {
            return ((double) mass/power) * 1.049;
        }
    }
}
```
Здесь мы добавили:
```java
public double accelerationToHundredTime() {
    return ((double) mass/power) * 1.049;
}
```
это **декларация метода (описание действия, но не само действие)**.   
Мы просто доводим до сведения программы то, что она должна уметь делать - т.е. возвращать время разгона до 100км\ч (по факту предоставлять результат вычисления `((double) mass/power) * 1.049)`).   
**Программа видит что в классе `Car` есть метод `accelerationToHundredTime()` т.е. он Декларирован. А значит умеет это делать.**  
Но уметь не значит делать! И она этого не делает.

##### ~~Инициализация~~ методов (ВЫЗОВ МЕТОДОВ!):
```java
public class Main {

    public static void main(String[] args) {
        System.out.println("Я программа у меня есть чертёж (декларация) машины");
        Car matiz = new Car("Красный", "Daewoo", "Matiz", "тРтрТртрТ", 55, 800);
        Car mustang = new Car("Жёлтый", "Ford", "Mustang", "ВррРРРР!!!", 500, 2100);
        System.out.println("По чертежам я создала 2 машины");
        System.out.println("Первая машина: " + mustang.mark + " " + mustang.model);
        System.out.println("Вторая машина: " + matiz.mark + " " + matiz.model);
        System.out.println("Я программа и я знаю, что машины умеют разгоняться, в зависимости от их массы и мощности, но пока я не разгоняла ни одну машину");
        System.out.println("Я разгоняю " + mustang.mark + " " + mustang.model + " " +
                mustang.engineSound + " он разогнался до 100 км/ч за " + mustang.accelerationToHundredTime() + " секунд!");
        System.out.println("Я разгоняю " + matiz.mark + " " + matiz.model + " " +
                matiz.engineSound + " он разогнался до 100 км/ч за " + matiz.accelerationToHundredTime() + " секунд!");
    }

    public static class Car {

        String color; //цвет
        String mark; //марка
        String model; //модель
        String engineSound; //звук двигателя
        int power; //мощность
        int mass; //масса

        /**
         * Конструктор класса Car (он ждёт данные по которым будет строить машину)
         */
        public Car(String color, String mark, String model, String engineSound, int power, int mass) {
            this.color = color;
            this.mark = mark;
            this.model = model;
            this.engineSound = engineSound;
            this.power = power;
            this.mass = mass;
        }

        /**
         * Метод расчета времени разгона до ста.
         * В зависимости от мощности и массы
         */
        public double accelerationToHundredTime() {
            return ((double) mass/power) * 1.049;
        }
    }
}
```
Добавилось ещё две строки! И надеюсь ты уже заметил - Там **вызывается** метод `accelerationToHundredTime()`.   
Вот я об этих участках `mustang.accelerationToHundredTime()` и `matiz.accelerationToHundredTime()`   
**Это по сути инициализация (ВЫЗОВ!)**  
Если честно для методов неправильно говорить инициализация. Метод это - действие.   
Для методов инициализация называется **вызовом**. Вызов метода это то, что программа реально делает, то, что мы ранее описали (декларировали).   
Ну и если ты всё правильно уложил в голове то уже должен понимать, что **один раз декларировав метод (научив программу) ты можешь бесконечное количество раз вызывать его там где тебе удобно!**

##### Теперь перейдём к переменным и напишем программу для их примера ~~декларации и~~ инициализации:
```java
public class Main {

    public static void main(String[] args) {
        System.out.println("Я программа у меня есть чертёж (декларация) машины");
        Car mustang;
        Car matiz;
        matiz = new Car("Красный", "Daewoo", "Matiz", "тРтрТртрТ", 55, 800);
        mustang = new Car("Жёлтый", "Ford", "Mustang", "ВррРРРР!!!", 500, 2100);
        System.out.println("По чертежам я создала 2 машины");
        System.out.println("Первая машина: " + mustang.mark + " " + mustang.model);
        System.out.println("Вторая машина: " + matiz.mark + " " + matiz.model);
        System.out.println("Я программа и я знаю, что машины умеют разгоняться, в зависимости от их массы и мощности, но пока я не разгоняла ни одну машину");
        System.out.println("Я разгоняю " + mustang.mark + " " + mustang.model + " " +
                mustang.engineSound + " он разогнался до 100 км/ч за " + mustang.accelerationToHundredTime() + " секунд!");
        System.out.println("Я разгоняю " + matiz.mark + " " + matiz.model + " " +
                matiz.engineSound + " он разогнался до 100 км/ч за " + matiz.accelerationToHundredTime() + " секунд!");
    }

    public static class Car {

        String color; //цвет
        String mark; //марка
        String model; //модель
        String engineSound; //звук двигателя
        int power; //мощность
        int mass; //масса

        /**
         * Конструктор класса Car (он ждёт данные по которым будет строить машину)
         *
         * На самом деле это тоже метод, такой метод декларирован внутри каждого класса явно (тобой) или неявно (по умолчанию, без параметров)
         * Мы вызываем его когда пишем "new Car(тут параметры которые нужно передать. ну те что ты видишь ниже!)"
         * Конструкторы нужны для того что бы создать объект класса, которому принадлежит конструктор (инициализировать).
         */
        public Car(String color, String mark, String model, String engineSound, int power, int mass) {
            this.color = color;
            this.mark = mark;
            this.model = model;
            this.engineSound = engineSound;
            this.power = power;
            this.mass = mass;
        }

        /**
         * Метод расчета времени разгона до ста.
         * В зависимости от мощности и массы
         */
        public double accelerationToHundredTime() {
            return ((double) mass/power) * 1.049;
        }
    }
}
```
Здесь я хочу что бы ты обратил внимание на этот участок кода:
```java
Car mustang; //объявление переменной 
Car matiz; //объявление переменной
mustang = new Car("Жёлтый", "Ford", "Mustang", 500, 2100); //инициализация переменной
matiz = new Car("Красный", "Daewoo", "Matiz", 55, 800); //инициализация переменной
```
Что мы видим?! У переменных **нет декларации**))) У них **ТОЛЬКО ИНИЦИАЛИЗАЦИЯ!**   
`Car mustang;` - **это не декларация!** Т.к. **декларация - это описание**. Мы здесь **не писали инструкцию или чертёж, это уже сделано** (класс `Car`)!   
Мы здесь как бы **подготовили место**.  

Раз мы в программе кодили про машины, то давай и проведём аналогию с машинами!   
Посмотрим внимательнее на:   
```java
Car mustang; //подготовили стенд для Мустанга 
Car matiz; //подготовили стенд для Матиза
```
здесь легко можно провести **аналогию со стендом для машин**. Т.е. машины ещё нет, но мы приготовили место под неё и написали на месте название той машины которую ждём.   
**На самом деле для программы это так и выглядит**, программа создаёт **ячейку в памяти** для каждой переменной когда ты её объявляешь, а имя переменной - это ссылка на эту ячейку. (чем не стенд?!)   
И нам ничего не мешает на стенд для мустанга поставить например матиз (и наоборот)   
вот смотри!
```java 
mustang = new Car("Красный", "Daewoo", "Matiz", 55, 800); //поставили матиз на стенд мустанга 
matiz = new Car("Жёлтый", "Ford", "Mustang", 500, 2100); //поставили мустанг на стенд матиза 
```
Код при этом всё-равно будет работать как обычно!
И когда мы "ставим машины на стенд" мы по сути присваиваем переменной значение!
Т.е. **инициализация для переменных проходит в 2 этапа** (ты их знаешь):  
1) **Объявление** - создаём переменную (например `Car mustang;`)
2) **Присвоение** - присваиваем значение (например `mustang = new Car("Красный", "Daewoo", "Matiz", 55, 800);`)   
_**ЗАМЕТЬ!** каждую машину делает **конструктор** `Car(параметры)` прежде, чем она будет отправлена на стенд!)   
Про конструктор написано в его комментарии в классе `Car` в коде **ВЫШЕ**_