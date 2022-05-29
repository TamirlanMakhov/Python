# Python

## Оглавление
-[Работа со строками](https://github.com/TamirlanMakhov/Python#Строки)

-[Работа с числами](https://github.com/TamirlanMakhov/Python#Числа)

-[Простые циклы](https://github.com/TamirlanMakhov/Python#Простые-циклы)

-[Списки, матрицы](https://github.com/TamirlanMakhov/Python#Списки)





-----------------------------------------------------------------------------------
#### Строки
1. Дана строка текста. Напишите программу для подсчета стоимости строки, исходя из того, что один любой символ (в том числе пробел) стоит 60 копеек. Ответ дайте в рублях и копейках в соответствии с примерами.
```python
s = input()
number_of_symbols = len(s)
print(number_of_symbols * 60 // 100, "р.", number_of_symbols * 60 % 100, "коп.")
```
2. На вход программе подается одна строка. Напишите программу, которая выводит:

общее количество символов в строке;
исходную строку повторенную 3 раза;
первый символ строки;
первые три символа строки;
последние три символа строки;
строку в обратном порядке;
строку с удаленным первым и последним символом.
```python
s = input()

length = len(s)
s_three_times = s * 3
first = s[0]
first_three = s[:3]
last_three = s[-3:]
reverse = s[::-1]
without_firs_and_last = s[1:-1]

print(length)
print(s_three_times)
print(first)
print(first_three)
print(last_three)
print(reverse)
print(without_firs_and_last)
```

3. Дано пятизначное или шестизначное натуральное число. Напишите программу, которая изменит порядок его последних пяти цифр на обратный.
```python
n = input()
if len(n) == 5:
    reverse = n[::-1]
    print(int(reverse))
if len(n) == 6:
    reverse = n[0] + n[:-6:-1]
    print(int(reverse))
```

4. На вход программе подается строка текста из натуральных чисел. Из элементов строки формируется список чисел. Напишите программу, которая меняет местами соседние элементы списка (a[0] c a[1], a[2] c a[3] и т.д.). Если в списке нечетное количество элементов, то последний остается на своем месте.
```python
s = input().split()

for i in range(0, len(s) - 1, 2):
    s[i], s[i+1] = s[i+1], s[i]
        
print(*s)
```

5. Дана строка текста, состоящая из букв русского алфавита "О" и "Р". Буква "О" – соответствует выпадению Орла, а буква "Р" – соответствует выпадению Решки. Напишите программу, которая подсчитывает наибольшее количество подряд выпавших Решек.
```python
s = input().split("О")

maximum = max(s, key=len)
print(len(maximum))
```
6. Необходимо написать программу, реализующую алгоритм написания этой песни. Алгоритм выводит в конце предложения следующую в алфавитном порядке букву, если она встречается в строке текста, а очередную строку отображает уже без этой буквы.
```python
alpha = ['а', 'б', 'в', 'г', 'д', 'е', 'ж', 'з', 'и', 'й', 'к', 'л', 'м', 'н', 'о', 'п', 'р', 'с', 'т', 'у', 'ф', 'х', 'ц', 'ч', 'ш', 'щ', 'ъ', 'ы', 'ь', 'э', 'ю', 'я']
word = input() + ' запретил букву'

for i in range(len(alpha)):
    if alpha[i] in word:
        print(word.strip(), alpha[i])
        word = word.replace(alpha[i], "")
        word = word.replace("  ", " ")
  ```
  
 9. Вводятся 3 строки в случайном порядке. Напишите программу, которая выясняет можно ли из длин этих строк построить возрастающую арифметическую прогрессию.
```python
# (2b-c-a)(2c-b-a)(2a-b-c) = 0 
a, b, c = len(input()), len(input()), len(input()),
if (2 * b - c - a) * (2 * c - b - a) * (2 * a - b - c) == 0:
    print("YES")
else:
    print("NO")
```

10. Будем считать email адрес корректным, если в нем есть символ собачки (@) и точки. Напишите программу проверяющую корректность email адреса.
```python
mail = input()
if "@" in mail and "." in mail:
    print("YES")
else:
    print("NO")
```

11. На вход программе подается строка текста, в которой буква «h» встречается минимум два раза. Напишите программу, которая удаляет из этой строки первое и последнее вхождение буквы «h», а также все символы, находящиеся между ними.
```python
s = input()

print(s[:s.find("h")], s[s.rfind("h") + 1:], sep="")
```

12. На вход программе подается строка текста. Если в этой строке буква «f» встречается только один раз, выведите её индекс. Если она встречается два и более раз, выведите индекс её первого и последнего вхождения на одной строке, разделенных символом пробела. Если буква «f» в данной строке не встречается, следует вывести «NO».
```python
s = input()
counter = ""

if s.count('f') == 1:
    print(s.find('f'))

elif s.count('f') >= 2:
    print(s.find('f'), s.rfind('f'), sep=" ")
else:
    print("NO")
```

13. На вход программе подается одна строка с буквами русского языка. Напишите программу, которая определяет количество гласных и согласных букв.
```python
s = input()
vowels = "ауоыиэяюёеАУОЫИЭЯЮЁЕ"
consonants = "бвгджзйклмнпрстфхцчшщБВГДЖЗЙКЛМНПРСТФХЦЧШЩ"

total_v = 0
total_c = 0

for i in s:
    if i in vowels:
        total_v += 1
    if i in consonants:
        total_c += 1
print("Количество гласных букв равно", total_v)
print("Количество согласных букв равно", total_c)
```

------------------------------------------------------------------------------------------------------------------------------------------------------
### Числа
1. Прогуливаясь по Манхэттену, вы не можете попасть из точки А в точку Б по кратчайшему пути. Если только вы не умеете проходить сквозь стены, вам обязательно придется идти вдоль его параллельно-перпендикулярных улиц. На плоскости манхэттенское расстояние между двумя точками (p_{1}; \, p_{2})(p 1 ​ ;p 2 ​ ) и (q_{1}; \, q_{2})(q 1 ​ ;q 2 ​ ) определяется так |p_{1}-q_{1}|+|p_{2}-q_{2}|∣p 1 ​ −q 1 ​ ∣+∣p 2 ​ −q 2 ​ ∣. Напишите программу определяющую манхэттенское расстояние между двумя точками, координаты которых заданы.
```python
p1, p2, q1, q2 = int(input()), int(input()), int(input()), int(input())
a = abs(p1 - q1) + abs(p2 - q2)
print(a)
```

2. Назовем число интересным, если в нем разность максимальной и минимальной цифры равняется средней по величине цифре. Напишите программу, которая определяет интересное число или нет. Если число интересное, следует вывести – «Число интересное» иначе «Число неинтересное».
```python
x = int(input())
a = x // 100  # 1 число из трехзначного
b = (x % 100) // 10  # 2 число из трехзначного
c = x % 10  # 3 число из трехзначного
if a > c and a - c == b :
    print("Число интересное")
elif c > a and c - a == b:
    print("Число интересное")
elif a < b == a + c:
    print("Число интересное")
else:
    print("Число неинтересное")
```
3. Правильный многоугольник — выпуклый многоугольник, у которого равны все стороны и все углы между смежными сторонами. Площадь правильного многоугольника с длиной стороны aa и количеством сторон nn вычисляется по формуле: 
![image](https://user-images.githubusercontent.com/104026290/170893880-ac97a90e-69c4-44a8-ad2e-1579932b403a.png)
```python
from math import *
n = int(input())
a = float(input())
s = (n * a**2)/(4 * tan(pi/n))
print(s)
```

4. Напишите программу, вычисляющую значение тригонометрического выражения по заданному числу градусов xx.
![image](https://user-images.githubusercontent.com/104026290/170893923-b6303c5c-5fbd-4144-91cf-262e08bf885e.png)

```python
from math import *

x = float(input())
r = radians(x)
s = sin(r) + cos(r) + tan(r)**2
print(s)
```

  
5. Напишите программу, которая считывает длины двух катетов в прямоугольном треугольнике и выводит его площадь
```python
a = float(input())
b = float(input())
s = 0.5 * a * b
print(s)
```

-------------------------------------------------------------------------------------------------------------------------------------------------
### Простые циклы
1. Дано натуральное число n (n<=9). Напишите программу, которая печатает таблицу размером n \times 3n×3 состоящую из данного числа (числа отделены одним пробелом).
```python
n = int(input())
for i in range(n):
    for j in range(3):
        print(n, end=" ")
    print()
  ```
  
2. Напишите программу, которая печатает таблицу размером n×5, где в i-ой строке указано число i (числа отделены одним пробелом).
  ```python
  n = int(input())
for i in range(1, n + 1):
    for j in range(5):
        print(i, end=" ")
    print()
```

3. Напишите программу, которая печатает таблицу сложения для всех чисел от 11 до n
```python
n = int(input())

for i in range(1, n + 1):
    for j in range(1, 10):
        print(i,  "+", j, "=", i + j)
    print()
```

4. Дано нечетное натуральное число n. Напишите программу, которая печатает равнобедренный звездный треугольник с основанием, равным n в соответствии с примером:
```python
n = int(input())

for i in range(1, (n + 1) // 2 + 1):
    print("*" * i)
for j in range((n - 2) // 2 + 1, 0, -1):
    print("*" * j)
 ```

5. Дано натуральное число n. Напишите программу, которая печатает численный треугольник в соответствии с примером:
![image](https://user-images.githubusercontent.com/104026290/170894199-b6991106-5994-4622-91e6-1ad86203b976.png)

```python
n = int(input())

for i in range(1, n + 1):
    for j in range(1, i + 1):
        print(i, end="")
    print()
```

6. На вход программе подается два натуральных числа a и b (a < b). Напишите программу, которая находит все простые числа от a до b включительно.
```python
a, b = int(input()), int(input())

for i in range(a, b + 1):
    count = 0
    for j in range(1, i + 1):
        if i % j == 0:
            count += 1
    if count == 2:
        print(i)
```

7. Дан набор точек на координатной плоскости. Необходимо подсчитать и вывести количество точек, лежащих в каждой координатной четверти.
![image](https://user-images.githubusercontent.com/104026290/170894342-44d4ab3c-9ece-4d0d-994c-dfcb99c3a609.png)

```python
first, second, third, fourth = 0, 0, 0, 0
for i in range(int(input())):
    xy = input().split()
    if int(xy[0]) > 0 and int(xy[1]) > 0:
        first += 1
    elif int(xy[0]) < 0 and int(xy[1]) < 0:
        third += 1
    elif int(xy[0]) > 0 and int(xy[1]) < 0:
        fourth += 1
    elif int(xy[0]) < 0 and int(xy[1]) > 0:
        second += 1
    
print("Первая четверть:", first)
print("Вторая четверть:", second)
print("Третья четверть:", third)
print("Четвертая четверть:", fourth)
```
---------------------------------------------------------------------------------------------------------------------------------------------------------
1. На вход программе подается число n. Напишите программу, которая создает и выводит построчно список, состоящий из n списков
![image](https://user-images.githubusercontent.com/104026290/170894412-aae95a0a-1f1d-43d6-8649-e42a2454f6fa.png)

```python
n = int(input())

lists = [[j for j in range(1, n+1)] for i in range(n)]
for i in lists:
    print(i)
```

2. На вход программе подается число nn. Напишите программу, которая возвращает указанную строку треугольника Паскаля в виде списка (нумерация строк начинается с нуля).
```python
from math import *

n = int(input())
triangle = []

for i in range(0, n+1):
    triangle.append(int((factorial(n)/(factorial(i)*factorial(n-i)))))

print(triangle)
```

3. На вход программе подается строка текста, содержащая символы. Напишите программу, которая упаковывает последовательности одинаковых символов заданной строки в подсписки.
```python
from itertools import groupby

s = input().split()
new = []

for i, j in groupby(s):
    new.append(list(j))
    
print(new)
```
4. На вход программе подаются две строки, на одной символы, на другой число n. Из первой строки формируется список.

Реализуйте функцию chunked(), которая принимает на вход список и число, задающее размер чанка (куска), а возвращает список из чанков указанной длины.
```python
def chunked(string, num):
    res = []
    for i in range(0, len(string), num):
        res.append(string[i:i+n])
    return res
        

s = input().split()
n = int(input())

print(chunked(s, n))
```
5. На вход программе подаются два натуральных числа n и m, каждое на отдельной строке — количество строк и столбцов в матрице. Далее вводятся сами элементы матрицы — слова, каждое на отдельной строке; подряд идут элементы сначала первой строки, затем второй, и т.д.

Напишите программу, которая сначала считывает элементы матрицы один за другим, затем выводит их в виде матрицы.
```python
n, m = int(input()), int(input())
matrix = []
d = [[input() for _ in range(m)] for _ in range(n)]

for r in range(n):
    for c in range(m):
        print(d[r][c], end=' ')
    print()
```

6. Следом квадратной матрицы называется сумма элементов главной диагонали. Напишите программу, которая выводит след заданной квадратной матрицы.
```python
n, matrix, sum1 = int(input()), [], []

for i in range(n):
    temp = [int(num) for num in input().split()]
    matrix.append(temp)

for r in range(n):
    if matrix[r][r]:
        sum1.append(matrix[r][r])

print(sum(sum1))
```

7. Напишите программу, которая выводит количество элементов квадратной матрицы в каждой строке, больших среднего арифметического элементов данной строки.
```python
n = int(input()) 
matrix = []

for i in range(n):
    temp = [int(num) for num in input().split()]
    matrix.append(temp)
    sum_row = sum(matrix[i])/n
    counter = 0
    for j in matrix[i]:
        if j > sum_row:
            counter += 1
    print(counter)
```

8. Квадратная матрица разбивается на четыре четверти, ограниченные главной и побочной диагоналями: верхнюю, нижнюю, левую и правую. Напишите программу, которая вычисляет сумму элементов: верхней четверти; правой четверти; нижней четверти; левой четверти.
![image](https://user-images.githubusercontent.com/104026290/170894693-64da463c-c46d-4468-9a29-c9bbc3d98c12.png)

```python
n, matrix, up, down, left, right = int(input()), [], [], [], [], []

for _ in range(n):
    row = [int(x) for x in input().split()]
    matrix.append(row)
    
for i in range(n):
    for j in range(n):
        if i < j:
            if i < n - 1 - j:
                up.append(matrix[i][j])
            elif i > n - 1 - j:
                right.append(matrix[i][j])
        if i > j:
            if i < n - 1 - j:
                 left.append(matrix[i][j])
            elif i > n - 1 - j:
                 down.append(matrix[i][j])
                             
print('Верхняя четверть:', sum(up))
print('Правая четверть:', sum(right))
print('Нижняя четверть:', sum(down))
print('Левая четверть:', sum(left))
```

9. На вход программе подаются два натуральных числа n и m — количество строк и столбцов в матрице. Создайте матрицу mult размером n×m и заполните её таблицей умножения по формуле mult[i][j] = i * j.
```python
n, m = int(input()), int(input())

matrix = [[str(i * j).ljust(3) for i in range(m)] for j in range(n)]
for r in range(n):
    for c in range(m):
        print(matrix[r][c], end=' ')
    print()
```

10. На вход программе подаются два натуральных числа n и m — количество строк и столбцов в матрице, затем n строк по m целых чисел в каждой, отделенных символом пробела.

Напишите программу, которая находит индексы (строку и столбец) первого вхождения максимального элемента.
```python
n, m = int(input()), int(input())
matrix = []
for _ in range(n):
    raw = [int(x) for x in input().split()]
    matrix.append(raw)
    
    
counter = 0
for i in range(n):
    for j in range(m):
        if counter >= 1:
            break
        if matrix[i][j] == max(max(matrix, key=max)):
            counter += 1
            print(i, j)
```

11. Напишите программу, которая меняет местами столбцы в матрице.На вход программе на разных строках подаются два натуральных числа n и m — количество строк и столбцов в матрице, затем элементы матрицы построчно через пробел, затем числа i и j — номера столбцов, подлежащих обмену.
```python
n, m = int(input()), int(input())  #  строка, столбец. 
matrix = [[int(x) for x in input().split()] for _ in range(n)]
from_to = input().split()
from_to_int = [int(num) for num in from_to]
first = from_to_int[0]
second = from_to_int[1]

for i in range(n):
    matrix[i][first], matrix[i][second] = matrix[i][second], matrix[i][first]
    
for i in range(n):
    for j in range(m):
        print(matrix[i][j], end=' ')
    print()
```

12. Напишите программу, которая проверяет симметричность квадратной матрицы относительно главной диагонали.
```python
n = int(input())
matrix = []
for _ in range(n):
    row = [int(num) for num in input().split()]
    matrix.append(row)
      
tr_matrix = [[0 for _ in range(len(matrix))] for _ in range(len(matrix[0]))]
for i in range(len(matrix)):
    for j in range(len(matrix[0])):
        tr_matrix[j][i] = matrix[i][j]

if matrix == tr_matrix:
    print("YES")
else:
    print("NO")
```

13. Дана квадратная матрица чисел. Напишите программу, которая зеркально отображает её элементы относительно горизонтальной оси симметрии.
```python
n = int(input())
matrix = [[int(x) for x in input().split()] for _ in range(n)]
matrix.reverse()

for i in range(n):
    for j in range(n):
        print(matrix[i][j], end=' ')
    print()
```

14. На шахматной доске 8×8 стоит конь. Напишите программу, которая отмечает положение коня на доске и все клетки, которые бьет конь. Клетку, где стоит конь, отметьте английской буквой N, клетки, которые бьет конь, отметьте символами *, остальные клетки заполните точками.
![image](https://user-images.githubusercontent.com/104026290/170894828-291d3fd8-d01c-4f89-a875-206e9beab167.png)

```python
coordinates = input()
matrix = []
for i in range(8):
    matrix.append(['.'] * 8)  # заполняем точками

# переводим шахматные координаты в индексы матрицы
x = 8 - int(coordinates[1])
y = abs(97 - ord(coordinates[0]))
matrix[x][y] = 'N'

#ищем возможные позиции
for i in range(8):
    for j in range(8):
        if abs((x - j) * (y - i)) == 2:
            matrix[j][i] = '*'

for row in matrix:
    print(*row)
```

15. Напишите программу, которая перемножает две матрицы. На вход программе подаются два натуральных числа nn и mm — количество строк и столбцов в первой матрице, затем элементы первой матрицы, затем пустая строка. Далее следуют числа m и k — количество строк и столбцов второй матрицы затем элементы второй матрицы.
```python
n, m = [int(i) for i in input().split()]
matrixA = [[int(i) for i in input().split()] for _ in range(n)]
input()
m, k = [int(i) for i in input().split()]
matrixB = [[int(i) for i in input().split()] for _ in range(m)]
matrixC = [[0] * k for _ in range(n)]

for i in range(n):
    for j in range(k):
        for q in range(m):
            matrixC[i][j] += matrixA[i][q] * matrixB[q][j]

for row in matrixC:
    print(*row)
```



