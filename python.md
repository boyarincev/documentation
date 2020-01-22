## Python

### Looping cheat sheet

[https://treyhunner.com/2016/04/how-to-loop-with-indexes-in-python/](https://treyhunner.com/2016/04/how-to-loop-with-indexes-in-python/)

Here’s a very short looping cheat sheet that might help you remember the preferred construct for each of these three looping scenarios.

Loop over a single list with a regular for-in:

```py
for n in numbers:
    print(n)
```

Loop over multiple lists at the same time with zip:

```py
for header, rows in zip(headers, columns):
    print("{}: {}".format(header, ", ".join(rows)))
```

Loop over a list while keeping track of indexes with enumerate:

```
for num, line in enumerate(lines):
    print("{0:03d}: {}".format(num, line))
```

### Lists

[https://pythonworld.ru/tipy-dannyx-v-python/spiski-list-funkcii-i-metody-spiskov.html](https://pythonworld.ru/tipy-dannyx-v-python/spiski-list-funkcii-i-metody-spiskov.html)

```
list.insert(index, val)
```

Допустим в массиве 4 элемента, мы делаем инсерт элемента на индекс 5 - в этом случае фактически элемент встанет на место с индексом 4, то есть инсерт не сможет дозаполнить недостающие элементы в списке.

[https://stackoverflow.com/q/45085089/5402731](https://stackoverflow.com/q/45085089/5402731)

Клонировать список: [https://stackoverflow.com/questions/2612802/how-to-clone-or-copy-a-list](https://stackoverflow.com/questions/2612802/how-to-clone-or-copy-a-list)

Разбор нюансов использования индексаторов: [https://towardsdatascience.com/the-basics-of-indexing-and-slicing-python-lists-2d12c90a94cf](https://towardsdatascience.com/the-basics-of-indexing-and-slicing-python-lists-2d12c90a94cf)

### Строки

Интерполяция строк: [https://www.programiz.com/python-programming/string-interpolation](https://www.programiz.com/python-programming/string-interpolation)

### Сортировка

[https://docs.python.org/3/howto/sorting.html](https://docs.python.org/3/howto/sorting.html)

### Словари

[https://pythonworld.ru/tipy-dannyx-v-python/slovari-dict-funkcii-i-metody-slovarej.html](https://pythonworld.ru/tipy-dannyx-v-python/slovari-dict-funkcii-i-metody-slovarej.html)

