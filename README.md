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
