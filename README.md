# ArduinoPet

*Оборудование -  Лазерный гравер ,  3D-принтер Prusa ,Инструменты fablab*

*Электроника - Сервопривод , провода ,  Arduino Uno*

*Кормушка сделана из PLA , подставка из фанерного  листа , крепление из ботлтов и  клея*

3D-модели  деталей кормушки 

![rjhv](https://github.com/ALEXKORNEEV2000/ArduinoPet/assets/85906021/19acc5af-f6ea-444a-92d8-70a0c097bf69)

![rjhv2](https://github.com/ALEXKORNEEV2000/ArduinoPet/assets/85906021/df21d2d0-21a1-4c91-9b5d-c6e492e44bc2)

![rjhv3](https://github.com/ALEXKORNEEV2000/ArduinoPet/assets/85906021/535188b4-b0d1-4ac7-bbf0-bbb8c324a9c6)



Распечатанная кормушка 


![готовая](https://github.com/ALEXKORNEEV2000/ArduinoPet/assets/85906021/55e2b588-5f80-4cb1-945f-a732a8480ff0)




Видео процесса работы устройства 

https://drive.google.com/file/d/123HI_0JTGXV3K-wz2y43SDjr4D_inx7d/view?usp=sharing


Аккуратный вариант ( расположили плату с боку  ) 

https://drive.google.com/file/d/1Q8ES46cwIMaKRLm-hqBax3EypEyOd7JF/view?usp=sharing



**Программный код**

``` Arduino 
#include <Servo.h> // библиотека сервопривода
Servo servo; // объявляем переменную servo типа "servo" 
int kek_pin = 2; // пин кнопки
int kek_stage = 0; // для хранения кнопки
void setup () {
servo.attach(10);// // привязываем сервопривод к аналоговому выходу 10
pinMode (kek_pin, INPUT); // Инициализируем цифровой вход/выход в режиме входа.
void loop() {
kek_stage = digitalRead( kek_pin) ; считываем значения с входа кнопки
if (kek_stage == HIGH) {
servo.write(180); //поворот на 180 
}
delay (2000); // задержка 
else  servo.write (360)
      }
    }
}
```

***Доработанная версия***

Улучшили модель и сделали ее больше для лучшей проходимости конфет 

![photo_2023-12-27_17-51-36](https://github.com/ALEXKORNEEV2000/ArduinoPet/assets/85906021/96c6ba01-3a80-4ccd-a481-fca16ce8bf11)


Также использовали сервопривод другого типа , который позволил изменить взаимодействие с устройством и способом взаимодействия с кормушкой 

Теперь кормушка будет работать пока нажата кнопка и перестанен работать , если кнопка не будет зажата 

**Программный код**

``` Arduino 
#include <Servo. h>
Servo servo;
int button pin = 2;
int buttonState = HIGH; // Изначальное состояние кнопки (не нажата)
void setup() f
pinMode (button pin, INPUT PULLUP);
servo. attach (10);
servo.write(0); // Устанавливаем исходную позицию сервопривода
void loop() f
buttonState = digitalRead(button _pin) ;
if (buttonState == HIGH) { // Если кнопка не нажата
while (buttonState == HIGH) {
servo.write(90);
// Поворачиваем сервопривод до 90 прадусов
}
buttonState = digitalRead(button pin); // Проверяем состояние кнопки
servo.write(0); // Возвращаем сервопривод в исходное положение
}
}
```
Концепция выдачи конфет :

Конфеты выдаются за оценки студента.
В зависмости от оценки студент должен зажать кнопку на определенное количество секунд 

***Тройка - 1 секунды***

***Четверка - 2 секунды***

***Пятерка - 3 секунды***



Добавил  резервуар-воронку  для хранилища конфет 

Добавил  подставку для красивого оформления 

Закрепил плату с боку и спрятал провод 


Процесс работы кормушки 



https://drive.google.com/file/d/1cbu5xKl6hedGNtI60zND7aVAYbMbZI09/view?usp=sharing


Итог сборки 

![photo_2023-12-29_11-41-08](https://github.com/ALEXKORNEEV2000/ArduinoPet/assets/85906021/58a5a089-66e9-43ac-a1aa-125eabe1a221)




