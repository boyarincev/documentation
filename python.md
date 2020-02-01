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

```text
all[True, False]) #Возвращает True, если все элементы списка истинны
any([True, False]) #Любой элемент истинен

orOp = True or False
andOp = True and False
```

