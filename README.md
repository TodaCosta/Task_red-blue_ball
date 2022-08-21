## Красные и синие шарики Python.
⦁	Написать функцию, которая будет выводить количество шариков (синие + красные) на итерации n.
![Image alt](https://github.com/TodaCosta/Task_red-blue_ball/blob/main/002.jpg)

Считаем количество синих шариков с помощью функции 
<br/>
центрированного пятиугольного числа (5*n**2-5*n+2)/2
```python
def ball(n):

    blue = 1
    red = 0

    b1, r1 = "синий", "красный"
    b2, r2 = "синих", "красных"
    if blue % 10 == 1:
        b = b1
    else:
        b = b2
    if red % 10 == 1:
        r = r1
    else:
        r = r2

    if n < 0:
        print("Введите n >= 0")
        return ball(int(input()))
    else:
        blue = int((5*n**2-5*n+2)/2)
        red = int(5 * n)
        return print(f"{blue} {b} + {red} {r}")
ball(int(input()))

```
⦁	Дана функция f. Что выведет print #1 и print #2?
```python
def f(x):
    if getattr(f, "x", None) is None:
        f.x = x
f(6)
f(7)
print(f.x)  # 1
setattr(f, "x", 67)
print(f.x)  # 2

# 1 print(f.x) выведет 6
# 2 print(f.x)  выведет 67
"""
В # 1 мы передаем аргумент в функцию со значением 6, т.к. у f.x нет атрибута и по умолчанию он является None, то f.x присваивается значение аргумента функции x равное 6. Теперь у нас есть атрибут, поэтому значение 7 не будет присвоено. 
В #2 мы  устанавливаем новое значение атрибута, равное 67.
"""
```
⦁	Задан словарь d, Необходимо написать код, который выведет список значений словаря, в убывающем порядке.
```python
d = {
'a': 1,
'b': 2,
'c': 3,
'd': 4,
'e': 5,
'f': 6
}

print(sorted(d.values(), reverse=True)) # [6, 5, 4, 3, 2, 1]

```
⦁	Чем плох данный фрагмент кода? Как его можно улучшить?
```python
my_dict = {
    '1': 1,
    '2': 2,
    '3': 3
}

def MYFUNC(a, b, c):
    """ return max """
    try:
        if a > b and a > c:
            return a
        if b > a and b > c:
            return b
        if c > a and c > b:
            return c
    except:
        pass

a = my_dict['1']
b = my_dict['2']
c = my_dict['3']

print(MYFUNC(a, b, c))
```
```python
"""
Если потребуется передать поочерёдно все ключи словаря и найти максимум, то быстрее и проще будет передать словарь как аргумент функции, воспользоваться методом sorted и взять последнее значение в конце списка:
"""
my_dict = {
    '1': 1,
    '2': 2,
    '3': 3
}


def MYFUNC(**kwargs):
    """ return max """
    try:
        max_value = sorted(kwargs.values())[-1]
        """if need key of max_value:
            for key, values in kwargs.items():
                if values == maxValue:
                    return key"""
        return max_value
    except:
        pass


print(MYFUNC(**my_dict))

```

⦁	Из-за чего возникла данная ошибка?

Revision: 41652
(python: 2.7.12 (v2.7.12:d33e0cf91556, Jun 27 2016, 15:19:22) [MSC v.1500 32 bit (Intel)])
(Qt: 4.8.7)
01.09.2020 9:22:05: <type 'exceptions.NameError'>
(global name 'isTypeOMS' is not defined)
  File "src\Registry\RegistryWindow.py", line 2551, in requestNewEvent
  File "src\Events\CreateEvent.py", line 228, in requestNewEvent
  File "src\library\Utils.py", line 2087, in wrapper
  File "src\Events\CreateEvent.py", line 725, in createEvent
  File "src\Forms\F025\F025Dialog.py", line 540, in prepare
```python
"""
Обращение к переменной, которой не существует (не была объявлена, а в случае с Python - не присвоено никакое значение).
"""
```
