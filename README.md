## Красные и синие шарики Python.
⦁	Написать функцию, которая будет выводить количество шариков (синие + красные) на итерации n.
![Image alt](https://github.com/TodaCosta/Task_red-blue_ball/blob/main/002.jpg)

Считаем количество синих шариков с помощью функции центрированного пятиугольного числа (5*n**2-5*n+2)/2
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
