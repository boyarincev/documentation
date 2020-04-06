# Python

## Модули

```text
import re #обращение будет через префикс re
reg = re.compile([0-9])

import re as regex #импорт с заданным именем
reg2 = regex.compile([0-9])

from collections import defaultdict, Counter #импорт только нужных значений
```

## Функции

```text
y = lambda x: x+4 #пример использования лямбд

def my_print(message='сообщение по умолчанию') #дефолтное значение параметра
    print(message)
    
my_print(message='другое сообщение') #при вызове можно явно указывать параметр
```

## Исключения

```text
try
    print(0 / 0)
except ZeroDivisionError
    print('Нельзя делить на ноль')
```

## Slicing \(работает на списках и на строках и на чём-нибудь ещё\)

[https://stackoverflow.com/a/509295/5402731](https://stackoverflow.com/a/509295/5402731)

It's pretty simple really:

```text
a[start:stop]  # items start through stop-1
a[start:]      # items start through the rest of the array
a[:stop]       # items from the beginning through stop-1
a[:]           # a copy of the whole array
```

There is also the `step` value, which can be used with any of the above:

```text
a[start:stop:step] # start through not past stop, by step
```

The key point to remember is that the `:stop` value represents the first value that is _not_ in the selected slice. So, the difference between `stop` and `start` is the number of elements selected \(if `step` is 1, the default\).

## Looping cheat sheet

[https://treyhunner.com/2016/04/how-to-loop-with-indexes-in-python/](https://treyhunner.com/2016/04/how-to-loop-with-indexes-in-python/)

Here’s a very short looping cheat sheet that might help you remember the preferred construct for each of these three looping scenarios.

Loop over a single list with a regular for-in:

```python
for n in numbers:
    print(n)
```

Loop over multiple lists at the same time with zip:

```python
for header, rows in zip(headers, columns):
    print("{}: {}".format(header, ", ".join(rows)))
```

Loop over a list while keeping track of indexes with enumerate:

```text
for num, line in enumerate(lines):
    print("{0:03d}: {}".format(num, line))
```

## Списки

{% embed url="https://pythonworld.ru/tipy-dannyx-v-python/spiski-list-funkcii-i-metody-spiskov.html" %}

```text
x[-1] #последний элемент
x[:] #копирование списка

x = [1, 2, 3]
x.extend([4, 5, 6]) #добавить в список другой список

y = x + [4, 5, 6] #создаёт новый список

y.append(7) #добавить элемент в список

z, w  = [1, 2] #распаковка списка - если известно количество элементов
```

```text
list.insert(index, val)
```

Допустим в массиве 4 элемента, мы делаем инсерт элемента на индекс 5 - в этом случае фактически элемент встанет на место с индексом 4, то есть инсерт не сможет дозаполнить недостающие элементы в списке.

[https://stackoverflow.com/q/45085089/5402731](https://stackoverflow.com/q/45085089/5402731)

Клонировать список: [https://stackoverflow.com/questions/2612802/how-to-clone-or-copy-a-list](https://stackoverflow.com/questions/2612802/how-to-clone-or-copy-a-list)

Разбор нюансов использования индексаторов: [https://towardsdatascience.com/the-basics-of-indexing-and-slicing-python-lists](https://towardsdatascience.com/the-basics-of-indexing-and-slicing-python-lists-2d12c90a94cf) \(степпинг, слайсинг - это всё\)

## Кортежи

Можно назвать неизменяемыми списками. Можно использовать для возврата из функции нескольких значений.

```text
my_tuple = (1, 2)
my_tuple = 1, 2 #так тоже можно создать
```

## Строки

Интерполяция строк: [https://www.programiz.com/python-programming/string-interpolation](https://www.programiz.com/python-programming/string-interpolation)

## Сортировка

[https://docs.python.org/3/howto/sorting.html](https://docs.python.org/3/howto/sorting.html)

```text
x = [4, 1, 2, 3]
#Отсортировать список и поместить результат в новый список
y = sorted(x)

#Отсортировать на месте
x.sort()

x.sort(reverse=True) #Отсортировать по убыванию

#Вместо ключей для сортировки использовать результаты функции
x.sort(key=abs)
```

## Словари

{% embed url="https://pythonworld.ru/tipy-dannyx-v-python/slovari-dict-funkcii-i-metody-slovarej.html" %}

Для проверки наличия ключа в словаре можно использовать оператор `in`

```text
dict = {}
#попробовать получить значение по ключу, 
#а если его нет, то вернуть дефолтное значение
dictVal = dict.get('key', 0)
```

Использование dict comprehension для создания словаря

{% embed url="https://www.datacamp.com/community/tutorials/python-dictionary-comprehension" %}

### Словарь defaultdict

При попытке получить из него значение, для ключа, который ещё не добавлялся, будет использовать функцию без параметров, используемую при создании словаря, для добавления в словарь ключа со значением, которое возвратит эта функция

```text
from collections import defaultdict
dd_list = defaultdict(list) #будет инициировать пустым список
```

### Словарь Counter

Трансформирует последовательность в словарь, где ключам будут поставлены в соответствие частотности \(сколько раз этот элемент встречается в последовательности\).

```text
from collections import Counter
c = Counter(0, 1, 2, 3)

#напечатать два наиболее часто встречающихся числа
for number, count in c.most_common(2):
    print(str(number), count)
```

## Set \(Множества\)

Совокупность неупорядоченных элементов без повторов

{% embed url="https://docs.python.org/3/library/stdtypes.html\#set-types-set-frozenset" %}

```text
s = set()
s.add(1)
```

## Membership test operations

{% embed url="https://docs.python.org/3/reference/expressions.html\#membership-test-operations" %}

Присутствие элемента в списке можно проверить с помощью `in`

```text
if x in s:
    
```

Работает и для словарей тоже

## Истинность

Рассматривается как False:

* False
* None
* пустой список
* пустой словарь
* ""
* пустое множество
* 0
* 0.0

## Генераторы последовательностей

```text
even_num_squares = [x * x for x in range(100) if x % 2 == 0]

even_num_squares_dict = {x : x * x for x in range(100) if x % 2 == 0}

even_num_squares_set = {x * x for x in range(100) if x % 2 == 0}

pairs_with_inner_loop = [(x, y) for x in range(100)
                                for y in range(100)]
                                
#lazy генераторное выражение
lazy_evens_below_20 = (i for i in range(20) if i % 2 == 0)
```

## Случайные числа

```text
import random

four_uniform_randov = [random.random() for _ in range(4)]

#генерация одного и того же рандомного числа
random.seed(10)
random.random()
random.random()

#произовольно выбрать из range 3-6
random.randrange(3, 6)

#перемешать числа в списке
up_to_ten = range(10)
random.shuffle(up_to_ten)

#выборать случайное значение из списка
random.choice(up_to_ten)

lottery_numbers = range(60)
#выбрать несколько случайных элементов, без повторов
random.sample(lottery_numbers, 6)

#выбрать несколько случайных элементов, с повторами
[random.choice(random(60)) for _ in range(4)]
```

## Регулярные выражения

```text
import re
```

## Объектно-ориентированное программирование

```text
class Set:
    def __init__(self, values=None):
    #это конструктор
    self.dict = {}

    if values is not None:
        for value in values: self.add(value)

    def __repr__(self):
    #строковое представление класса
    #дописать реализацию метода
    
    def add(self, value):
    #дописать реализацию метода    
    
    def remove(self, value)
    #дописать реализацию метода
    
s = Set([1, 2, 3])
s.add(4)
```

## Функциональное программирование

```text
def exp(base, power)
    return base ** power
    
#каррирование
from functools import partial
two_to_the = partial(exp, 2)
```

### Переменные args и kwargs

Позволяют обращаться к переменным функции, либо как к кортежу, либо как к словарю.

```text
def magic(*args, **kwargs):
    print('безымянные аргументы, как кортеж:', args)
    print('аргументы по ключу:', kwargs)
    
magic(1, 2, key='word', key2='word2')

#напечатает:
#безымянные аргументы, как кортеж: (1, 2)
#аргументы по ключу: {'key': 'word', 'key2': 'word2'}
```

Позволяют обернуть функцию с произвольным количеством аргументов.

```text
def doubler(f):
    #получает параметры как кортеж
    def g(*args):
        #передает кортеж, как отдельные параметры
        #если передавать с двумя звёздочками, то распакует словарь
        #и передаст по ключам в функцию
        return 2 * f(*args)
    return g
    
def f2(x, y):
    return x+y
    
f2_doubler = doubler(f2)

print(f2_doubler(1, 2))
```

## Встроенные функции

### all и any

```text
all[True, False]) #Возвращает True, если все элементы списка истинны
any([True, False]) #Любой элемент истинен

orOp = True or False
andOp = True and False


```

### map

```text
def double(x):
    return x*2
    
xs = [1, 2, 3, 4, 5]
twice_xs = map(double, xs)

#может принимать несколько списков
def multiply(x, y): return x * y

products = map(multiply, [1, 2], [4, 5]) # [4, 10]
```

### filter

```text
def is_even(x): return x % 2 == 0

x_evens = filter(is_even, range(100))
```

### reduce

Выполняет свертку списка: объединяет первые два элемента, затем полученный результат со следующим элементов и так до конца, в результате в конце получается единственное значение, как результат

```text
from functools import reduce

x_product = reduce(lambda x, y: x * y, range(100))
```

### enumerate

Позволяет итерировать по списку, зная индекс элемента

```text
docs = []
for index, doc in enumerate(docs):
    do_something(index, doc)
```

### zip

Объединяет два \(и более\) списка и возвращает список кортежей, где каждый кортеж это объединение соответствущих элементов из обоих списков.

```text
list1 = [1, 2, 3]
list2 = [a, b, c]

list(zip(list2, list1)) #[(a, 1), (b, 2), (c, 3)]
```

Если списки разных длин, то функция прекратит работу, когда закончится один из списков.

Разъеденить список можно используя \*

```text
pairs = [(a, 1), (b, 2), (c, 3)]
#*pairs - распакует список и передаст в функцию каждый элемент
#как отдельный параметр
list(zip(*pairs)) # [(a, b, c), (1, 2, 3)]
```

