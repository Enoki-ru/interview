## Начало
---
Всех приветствую! Сегодня мы продолжим масштабную подготовку к собеседованиям, потому что уже в понедельник будет встреча с руководителем одного направления Сбера, поэтому хочется как можно лучше подготовиться к этому дню. ( #сбер )

>Требования от сбера:
> - знание принципов и инструментов работы с большими данными SQL/Python
> - знание основных портфельных риск-метрик
> - знания статистики, принципов мат. моделирования, концепции статистической проверки гипотез

![Тут было фото](Pasted%20image%2020230520130731.png) 

## #Python
---
В этом блоке задач будут разбираться только задачи по Python

**Задача 1**
- Создайте df и придумайте ей данные с именами и фамилиями


```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
df=pd.DataFrame({'Name':['Сергей','Дарья','Инга','Наташа'],'Фамилия':['Воронин','Балюк','Калиева','Дребезова']})
print(df)
```

         Name    Фамилия
    0  Сергей    Воронин
    1   Дарья      Балюк
    2    Инга    Калиева
    3  Наташа  Дребезова
    

**Задача 2**
- Добавьте этой таблице еще один столбец с возрастами


```python
df['Возраст']=[31,26,43,12]
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Фамилия</th>
      <th>Возраст</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Сергей</td>
      <td>Воронин</td>
      <td>31</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Дарья</td>
      <td>Балюк</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Инга</td>
      <td>Калиева</td>
      <td>43</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Наташа</td>
      <td>Дребезова</td>
      <td>12</td>
    </tr>
  </tbody>
</table>
</div>



**Задача 3**
- Добавьте в таблицу еще одного человека


```python
df.loc[len(df)]=['Саша','Сулимов',33]
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Фамилия</th>
      <th>Возраст</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Сергей</td>
      <td>Воронин</td>
      <td>31</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Дарья</td>
      <td>Балюк</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Инга</td>
      <td>Калиева</td>
      <td>43</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Наташа</td>
      <td>Дребезова</td>
      <td>12</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Саша</td>
      <td>Сулимов</td>
      <td>33</td>
    </tr>
  </tbody>
</table>
</div>



**Задача 4**
- Добавьте этой таблице еще два столбца со случайными распределениями. В одном на отрезке (5,8), в другом на отрезке (50,85).


```python
import random
df['zodiac_id']=[random.randrange(5, 8, 1) for i in range(len(df))]
df['Вес']=random.sample(range(50,86),len(df))
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Фамилия</th>
      <th>Возраст</th>
      <th>zodiac_id</th>
      <th>Вес</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Сергей</td>
      <td>Воронин</td>
      <td>31</td>
      <td>7</td>
      <td>80</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Дарья</td>
      <td>Балюк</td>
      <td>26</td>
      <td>6</td>
      <td>57</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Инга</td>
      <td>Калиева</td>
      <td>43</td>
      <td>7</td>
      <td>62</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Наташа</td>
      <td>Дребезова</td>
      <td>12</td>
      <td>6</td>
      <td>60</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Саша</td>
      <td>Сулимов</td>
      <td>33</td>
      <td>7</td>
      <td>68</td>
    </tr>
  </tbody>
</table>
</div>



**Задача 5**
- Создайте другую таблицу со знаками зодиака, и объедините эти две таблицы, используя zodiac_id ( #зодиак )


```python
ZODIAC_SIGNS = [
    "Aries",
    "Taurus",
    "Gemini",
    "Cancer",
    "Leo",
    "Virgo",
    "Libra",
    "Scorpio",
    "Sagittarius",
    "Capricorn",
    "Aquarius",
    "Pisces"
]
zodiac=pd.DataFrame({'Зодиак':ZODIAC_SIGNS})
zodiac

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Зодиак</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Aries</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Taurus</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Gemini</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Cancer</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Leo</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Virgo</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Libra</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Scorpio</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Sagittarius</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Capricorn</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Aquarius</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Pisces</td>
    </tr>
  </tbody>
</table>
</div>




```python
df=df.merge(zodiac,how='left', left_on='zodiac_id',right_index=True)
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Фамилия</th>
      <th>Возраст</th>
      <th>zodiac_id</th>
      <th>Вес</th>
      <th>Зодиак</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Сергей</td>
      <td>Воронин</td>
      <td>31</td>
      <td>7</td>
      <td>80</td>
      <td>Scorpio</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Дарья</td>
      <td>Балюк</td>
      <td>26</td>
      <td>6</td>
      <td>57</td>
      <td>Libra</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Инга</td>
      <td>Калиева</td>
      <td>43</td>
      <td>7</td>
      <td>62</td>
      <td>Scorpio</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Наташа</td>
      <td>Дребезова</td>
      <td>12</td>
      <td>6</td>
      <td>60</td>
      <td>Libra</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Саша</td>
      <td>Сулимов</td>
      <td>33</td>
      <td>7</td>
      <td>68</td>
      <td>Scorpio</td>
    </tr>
  </tbody>
</table>
</div>



**Задача 6**
- Выведите только тех людей, у которых вес менее 60кг


```python
df[df['Вес']<60]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>Фамилия</th>
      <th>Возраст</th>
      <th>zodiac_id</th>
      <th>Вес</th>
      <th>Зодиак</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Дарья</td>
      <td>Балюк</td>
      <td>26</td>
      <td>6</td>
      <td>57</td>
      <td>Libra</td>
    </tr>
  </tbody>
</table>
</div>



**Задача 6.1**
- Выведите таблицу с кол-вами людей каждого присутствующего зодиака (из-за того что они рандомно берутся, значения будут меняться)



```python
df.groupby('Зодиак', as_index=False) \
    .agg({'Name':'count'})
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Зодиак</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Libra</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Scorpio</td>
      <td>3</td>
    </tr>
  </tbody>
</table>
</div>



**Задача 7**
- Сделайте две функции, одна при вызове будет писать длинную строку слешов, вторая будет возвращать строку курсивом


```python
#Сделаем функции для удобства
def slesh():
    print(f"\n---------------------------------------\n")
def italic(word): #Делает текст курсивным
    word='\x1B[3m'+word+'\x1B[0m'
    return word
```


```python
slesh()
print(f'Проверка {italic("правильной работы")} функций')
```

    
    ---------------------------------------
    
    Проверка [3mправильной работы[0m функций
    

**Задача 8**
- Назовите разницу между списком и кортежем


```python
# Назовите разницу между списком и кортежем

print('Список - изменяемый тип данных, который представляет собой в основном данные одного типа.')
names=['Darya','Sergey','Natalya','Ingochka','Timur','Sasha','Keril','Nastya']
for i,name in enumerate(names):
    print(f"{i}. {name}")

slesh()

print('Кортеж - неизменяемый тип данных. После создания его уже нельзя изменить.\nОднако, у него есть преимущества: \
      \n1. Он оптимизирован, поэтому с ним работать быстрее \
      \n2. Это безопасно, потому что данные нельзя никак изменить \
      \n3. В нем часто хранятся различные типы данных')
cortege=(3.98,'Sergey','2023-05-09')
print(cortege)
for i in cortege:
    print(i)
```

    Список - изменяемый тип данных, который представляет собой в основном данные одного типа.
    0. Darya
    1. Sergey
    2. Natalya
    3. Ingochka
    4. Timur
    5. Sasha
    6. Keril
    7. Nastya
    
    ---------------------------------------
    
    Кортеж - неизменяемый тип данных. После создания его уже нельзя изменить.
    Однако, у него есть преимущества:       
    1. Он оптимизирован, поэтому с ним работать быстрее       
    2. Это безопасно, потому что данные нельзя никак изменить       
    3. В нем часто хранятся различные типы данных
    (3.98, 'Sergey', '2023-05-09')
    3.98
    Sergey
    2023-05-09
    

**Задача 9**
- Перечислите все методы вывода переменной в функции print()


```python
slesh()
name='Сергей'

print(f"Меня зовут {name}")
slesh()
print("Меня зовут %s" % name)
slesh()
print("Меня зовут {}".format(name))
slesh()
```

    
    ---------------------------------------
    
    Меня зовут Сергей
    
    ---------------------------------------
    
    Меня зовут Сергей
    
    ---------------------------------------
    
    Меня зовут Сергей
    
    ---------------------------------------
    
    

**Задача 10**
- Существует ли разница между операциями сравнения `is` и `==` ?


```python
print("На самом деле, всё просто: \n\
    Операция is сравнивает адреса на объекты, и если они одинаковые, то выводит True. Давайте убедимся в этом")
a=[1,2,3]
b=[1,2,3]
print(a==b)
print(f'Добавим третью переменную, которая будет ссылаться на a={a}')
c=a
print(f"a is b = {a is b}")
print(f"a is c = {a is c}")
print(f"b is c = {b is c}")
slesh()
print('Оказывается, мы даже можем узнать их адреса, и сами тогда убедимся, что они разные')
print(f"id(a) = {id(a)}")
print(f"id(b) = {id(b)}")
print(f"id(c) = {id(c)}")
```

    На самом деле, всё просто: 
        Операция is сравнивает адреса на объекты, и если они одинаковые, то выводит True. Давайте убедимся в этом
    True
    Добавим третью переменную, которая будет ссылаться на a=[1, 2, 3]
    a is b = False
    a is c = True
    b is c = False
    
    ---------------------------------------
    
    Оказывается, мы даже можем узнать их адреса, и сами тогда убедимся, что они разные
    id(a) = 1732762595776
    id(b) = 1732762532288
    id(c) = 1732762595776
    

**Задача 11**
- Что такое #декоратор ?


```python
print('Если простыми словами, то это функционал, который позволяет добавить новую функциональность в уже существующую функцию')
print('Как это делается: Функция передается декоратору, а он выполняет и существующий, и дополнительный код')
slesh()
print(f'Вас спросят: {italic("Напишите пример декоратора")}')

def benchmark(func):
    import time

    def wrapper():
        start = time.time()
        func()
        end = time.time()
        print('[*] Время выполнения: {} секунд.'.format(end-start))
    return wrapper

@benchmark
def fetch_webpage():
    import requests
    webpage = requests.get('https://google.com')

fetch_webpage()

print(f'Теперь рассказываем, что здесь произошло. \
    \nДля начала мы создали декоратор - функцию {italic("benchmark")}, которая принимает в себя другую функцию. \
    \nИ судя по строкам в ней, она после вызова себя начнет отсчет времени выполнения самой функции, которую мы туда поместим! \
    \nТолько теперь уже после написания {italic("@benchmark")} мы переобозначим функцию, которую сами же и напишем, добавляя туда элемент подсчета времени выполнения.')
slesh()
```

    Если простыми словами, то это функционал, который позволяет добавить новую функциональность в уже существующую функцию
    Как это делается: Функция передается декоратору, а он выполняет и существующий, и дополнительный код
    
    ---------------------------------------
    
    Вас спросят: [3mНапишите пример декоратора[0m
    [*] Время выполнения: 0.3961973190307617 секунд.
    Теперь рассказываем, что здесь произошло.     
    Для начала мы создали декоратор - функцию [3mbenchmark[0m, которая принимает в себя другую функцию.     
    И судя по строкам в ней, она после вызова себя начнет отсчет времени выполнения самой функции, которую мы туда поместим!     
    Только теперь уже после написания [3m@benchmark[0m мы переобозначим функцию, которую сами же и напишем, добавляя туда элемент подсчета времени выполнения.
    
    ---------------------------------------
    
    

**Задача 12**
- Приведите пример использования класса ( #класс )


```python
def funfun(word):
    print(f'Прикинь, когда я к нему подошел, он сказал {word}')

class hero:
    def __init__(self,name):
        self.name=name
        print(f"Привет, {self.name}!")
    def show_name(self):
        self.say="Меня зовут "+self.name
        return self.say

ser=hero('Сергей')
funfun(ser.show_name())
```

    Привет, Сергей!
    Прикинь, когда я к нему подошел, он сказал Меня зовут Сергей
    

**Задача 13**
- Расскажите особенности использования функции #range 



```python
for i in range(5):
    print(i,end='')
slesh()
for i in range(2,7):
    print(i,end='')
slesh()
for i in range(2,7,2):
    print(i,end='')
slesh()
print(italic("Как создать список с использованием range в одну строчку?"))
print('Ответ убил:\n')
print('[i for i in range(10)]')
[i for i in range(10)]

```

    01234
    ---------------------------------------
    
    23456
    ---------------------------------------
    
    246
    ---------------------------------------
    
    [3mКак создать список с использованием range в одну строчку?[0m
    Ответ убил:
    
    [i for i in range(10)]
    




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]



**Задача 14**
- Определите класс car с двумя атрибутами: color и speed. Затем создайте экземпляр и верните speed




```python
class car:
    def __init__(self,color,speed):
        self.color=color
        self.speed=speed
bmw_andrey=car('Черный',180)
bmw_sergey=car('Белый',220)
bmw_sergey.color
bmw_sergey.speed
bmw_andrey.speed
```




    180



**Задача 15**
- Покажите пример использования функции #map , и расскажите, что это такое





```python
print("Функция map перебирает значения, применяя какую-то другую функцию к каждому элементу")
print('Пример:')
scores=[33,55,47,58,49,30,43,54,35,46,51,47,59,56,53,56,47,39,20,52]
def procents(num):
    return str((num/100))+'%'
print(f"Вот следующие проценты выполнения работ учеников:\n \
      {list(map(procents,scores))}")
```

    Функция map перебирает значения, применяя какую-то другую функцию к каждому элементу
    Пример:
    Вот следующие проценты выполнения работ учеников:
           ['0.33%', '0.55%', '0.47%', '0.58%', '0.49%', '0.3%', '0.43%', '0.54%', '0.35%', '0.46%', '0.51%', '0.47%', '0.59%', '0.56%', '0.53%', '0.56%', '0.47%', '0.39%', '0.2%', '0.52%']
    

**Задача 16**
- Объясните, как работает функция #filter






```python
print('Функция делает буквально то, о чем говорит ее название: она фильтрует элементы в последовательности. \
    \nКаждый элемент передается функции, которая включает его в последовательность, если по условию получает True, и отбрасывает в случае False:')
def add_three(x):
    if x % 3 == 0:
        return True        
    else:
        return False

li = [i for i in range(1,100)]
print('Было:')
print(li[:20],'<...>')
q=[i for i in filter(add_three, li)]
print('Стало:')
print(q)
```

    Функция делает буквально то, о чем говорит ее название: она фильтрует элементы в последовательности.     
    Каждый элемент передается функции, которая включает его в последовательность, если по условию получает True, и отбрасывает в случае False:
    Было:
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20] <...>
    Стало:
    [3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57, 60, 63, 66, 69, 72, 75, 78, 81, 84, 87, 90, 93, 96, 99]
    

**Задача 17**
- Что такое изменяемые и неизменяемые объекты. Назовите изменяемые и неизменяемые объекты.



```python
print('Изменяемыми объектами называются те, которые можно изменить без изменения адреса объекта. Такими являются:\nlist\ndict\nset')
print("Изменяемые: int, float, bool, string и tuple.")
```

    Изменяемыми объектами называются те, которые можно изменить без изменения адреса объекта. Такими являются:
    list
    dict
    set
    Изменяемые: int, float, bool, string и tuple.
    


```python

```


```python

```
