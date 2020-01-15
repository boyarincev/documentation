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

```
list.insert(index, val)
```

Допустим в массиве 4 элемента, мы делаем инсерт элемента на индекс 5 - в этом случае фактически элемент встанет на место с индексом 4, то есть инсерт не сможет дозаполнить недостающие элементы в списке.

https://stackoverflow.com/q/45085089/5402731

