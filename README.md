# CatMove
Найди логическую ошибку: утка (Duck) должна корректно реализовывать интерфейс CanMove.
Исправь ошибку. Результат вывода в консоль должен быть таким:
Flying
Moving

package com.java.task.task15.task1520;

/*
Тренировка мозга
*/

public class Solution {
    public static void main(String[] args) {
        Duck duck = new Duck();
        Util.fly(duck);
        Util.move(duck);
    }

    public static class Duck implements CanFly, CanMove {
        @Override
        public void doAction() {
            System.out.println("Flying");
        }
    }

    public static class Util {
        static void fly(CanFly animal) {
            animal.doAction();
        }

        static void move(CanMove animal) {
            animal.doAction();
        }
    }

    public static interface CanFly {
        void doAction();
    }

    public static interface CanMove {
        void doAnotherAction();
    }
}


Псевдокод 

```
ПАКЕТ com.javarush.task.task15.task1520

КЛАСС Solution:
    ГЛАВНАЯ функция main:
        СОЗДАТЬ утку = НОВАЯ Утка()
        Вызвать Util.лететь(утка)
        Вызвать Util.двигаться(утка)
    КОНЕЦ main

    КЛАСС Утка РЕАЛИЗУЕТ МожетЛетать, МожетДвигаться:
        ПЕРЕОПРЕДЕЛИТЬ функция делатьДействие():
            ВЫВЕСТИ "Flying"
        КОНЕЦ функции

        ПЕРЕОПРЕДЕЛИТЬ функция делатьДругоеДействие():
            ВЫВЕСТИ "Moving"
        КОНЕЦ функции
    КОНЕЦ КЛАССА Утка

    КЛАСС Утилита:
        СТАТИЧЕСКАЯ функция лететь(животное МожетЛетать):
            животное.делатьДействие()
        КОНЕЦ функции

        СТАТИЧЕСКАЯ функция двигаться(животное МожетДвигаться):
            животное.делатьДругоеДействие()
        КОНЕЦ функции
    КОНЕЦ КЛАССА Утилита

    ИНТЕРФЕЙС МожетЛетать:
        функция делатьДействие()
    КОНЕЦ ИНТЕРФЕЙСА

    ИНТЕРФЕЙС МожетДвигаться:
        функция делатьДругоеДействие()
    КОНЕЦ ИНТЕРФЕЙСА
КОНЕЦ КЛАССА Solution
```

Что происходит в программе:

1. Создаётся объект Duck (утка)
2. В метод Util.fly() передаётся утка как CanFly, вызывается doAction() → выводится "Flying"
3. В метод Util.move() передаётся утка как CanMove, вызывается doAnotherAction() → выводится "Moving"

Вывод программы:

```
Flying
Moving
```
