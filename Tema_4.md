# Тема 4. Функции и модули
Отчет по Теме #4 выполнил(а):
- Свинцова Софья Александровна
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ |---------|---------|
| Задание 1 | +       | +       |
| Задание 2 | +       | +       |
| Задание 3 | +       | +       |
| Задание 4 | +       | +       |
| Задание 5 | +       | +       |
| Задание 6 | +       | -       |
| Задание 7 | +       | -       |
| Задание 8 | +       | -       |
| Задание 9 | +       | -       |
| Задание 10 | +       | -       |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №4
#1.

```python
def main():
    print(2 + 2)
    
if __name__ == '__main__':
    main()
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/1.png)

#2. 

```python
def main():
    result = 2 + 2
    return result

if __name__ == '__main__':
    answer = main()
    print(answer)
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/2.png)


#3.

```python
def main(one, two):
    result = one + two
    return result

for i in range(5):
    x = 1
    y = 10
    answer = main(x, y)
    print(answer)
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/3.png)


#4.

```python
def main(x, *args):
    one = x
    two = sum(args)
    three = float(len(args))
    print(f"one={one}\ntwo={two}\nthree={three}")

    return x + sum(args) / float(len(args))

if __name__ == '__main__':
    result = main(10, 0, 1, 2, -1, 0, -1, 1, 2)
    print(f"\nresult={result}")
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/4.png)


#5. 
```python
def main(**kwargs):
    for i in kwargs.items():
        print(i[0], i[1])

    print()

    for key in kwargs:
        print(f"{key} = {kwargs[key]}")

if __name__ == '__main__':
    main(x=[1, 2, 3], y=[3, 3, 0], z=[2, 3, 0], q=[3, 3, 0], w=[3, 3, 0])
    print()

    main(**{'x': [1, 2, 3], 'y': [3, 3, 0]})
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/5.png)


#6.

```python
def main(**kwargs):
    for i, j in kwargs.items():
        print(f"{i}. Mean = {mean(j)}")
        
def mean(data):
    return sum(data) / float(len(data))

if __name__ == '__main__':
    main(x=[1, 2, 3], y=[3, 3, 0])
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/6.png)


#7. 

```python
def say_hello():
    print('Hello students')
```

```python
from for_import import say_hello

if __name__ == '__main__':
    say_hello()
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/7.png)


#8. 

```python
import math

def main():
    value = int(input('ВВедите значение: '))
    print(math.sqrt(value))
    print(math.sin(value))
    print(math.cos(value))

if __name__ == '__main__':
    main()
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/8.png)


#9. 

```python
from datetime import datetime as dt
from datetime import timedelta as td

def main():
    print(
        f"Сегодня {dt.today().date()}. "
        f"День недели - {dt.today().isoweekday()}"
    )
    n = int(input('Введите количество дней: '))
    today = dt.today()
    result = today + td(days=n)
    print(
        f"Через {n} дней будет {result.date()}. "
        f"День недели - {result.isoweekday()}"
    )

if __name__ == '__main__':
    main()
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/9.png)


#10. 

```python
global result

def rectangle():
    a = float(input("Ширина: "))
    b = float(input("Высота: "))
    global result
    result = a * b

def triangle():
    a = float(input("Основание: "))
    h = float(input("Высота: "))
    global result
    result = 0.5 * a * h

figure = input("1-прямоугольник, 2-треугольник: ")

if figure == '1':
    rectangle()
elif figure == '2':
    triangle()

print(f"Площадь: {result}")

```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/лаб4/10.png)



## Самостоятельная работа №4
#1

```python
from datetime import datetime # импорт библиотеки datetime
from math import sqrt # импорт библиотеки math

def main(**kwargs):
  """
          Подсчитывается корень из квадратов чисел
        из входного двумерного массива

         args:
         kwargs(кортеж): Массив
         returns:
         результат: корень из квадратов введенных чисел.
    """
  for key in kwargs.items():
        result = sqrt(key[1][0] ** 2 + key[1][1] ** 2)
        print(result)



if __name__ == '__main__': # входная точка
    start_time = datetime.now() # сохраняется текущее время
    main(
        one=[10, 3],
        two=[5, 4],
        three=[15, 13],
        four=[93, 53],
        five=[133, 15]
    ) # входные данные
    time_costs = datetime.now() - start_time # находится время выполнения программы
    print(f"Время выполнения программы - {time_costs}")
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/сам4/1.png)

### Вывод
использовав символ # прокомментировала строки кода, кроме функции, а функция была задокументирована при помощи ковычек

#2

```python
import random

def play():
    num = random.randint(1, 6)
    print(f"Кубик: {num}")
    if num in [5, 6]:
        print("Вы победили")
    elif num in [3, 4]:
        play()
    else:
        print("Вы проиграли")

if __name__ == "__main__":
    play()
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/сам4/2.png)

### Вывод
с помощью ф-ции random генерируется случайное число, при помощи рекурсивной функции происходит сама игра
  
#3

```python
import datetime
import time

for i in range(5):
    current_time = datetime.datetime.now()
    print(current_time.strftime("%H:%M:%S"))
    time.sleep(1)
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/сам4/3.png)

### Вывод
импортируем datetime и time, выводим время и затем с помощью time.sleep усыпляем время на 1 секунду
  
#4

```python
def average(*args):
    return sum(args) / len(args)

if __name__ == "__main__":
    print(average(3, 5, 7))
    print(average(1, 2, 3, 4, 5))
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/сам4/4.png)

### Вывод 
возвращается среднее арифметическое
  
#5

```python
def calculate(a, b, c):
    s = (a + b + c) / 2
    area = (s * (s - a) * (s - b) * (s - c)) ** 0.5
    return area
```
```python
from err import calculate

a = float(input("Введите длину стороны a: "))
b = float(input("Введите длину стороны b: "))
c = float(input("Введите длину стороны c: "))

area = calculate(a, b, c)
print(f"Площадь треугольника: {area}")
```
### Результат.

![Меню](https://github.com/ssselfish/SoftwareEngineering/blob/Тема_4/сам4/5.png)
### Вывод 
вычисляется площадь треугольника и импортируются файл и метод

## Общий вывод 
Были изучены функции, рекурсивные функции, разобраны аргументы функции и параметры, использование кортежа. Также изучено документирование функции и глобальные переменные.
 
