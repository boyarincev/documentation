# Jupyter Notebook

## Сервер

Запустить сервер

> jupyter notebook

[http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html](http://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/execute.html)

Управление окружением - conda

conda - это anaconda - дистрибутив на основе Python для математических вычислений

[https://conda.io/docs/user-guide/tasks/manage-environments.html](https://conda.io/docs/user-guide/tasks/manage-environments.html)

|  |  |
| :--- | :--- |
| conda create -n py27 python=2.7.9 anaconda | Создать среду с названием py27 и установить туда python версии 2.7 |
| source activate py27 | Переключиться на использование среды py27 |
| deactivate | Деактивировать текущую среду, вернуться в среду по умолчанию |
| python --version | Узнать какую версию использует текущая среда |
| conda remove -n py27 --all | Удалить среду py27, а после выполнить conda clean --lock |
| conda install --name py27 scypy | Установить библиотеку scypy  в среду py27 |
| conda remove --name py27 scypy | Удалить библиотеку scypy в среде py27 |
| conda clean --lock | Очистить блокировку, если произошёл сбой при установке среды |
|  |  |

**С помощью environments можно использовать разные версии python работая с одной инсталляцией anaconda**

### [Viewing a list of your environments](https://conda.io/docs/user-guide/tasks/manage-environments.html#id8)

To see a list of all of your environments, in your Terminal window or an Anaconda Prompt, run:

```text
conda info --envs
```

### [Activating an environment](https://conda.io/docs/user-guide/tasks/manage-environments.html#id5)

To activate an environment:

* On Windows, in your Anaconda Prompt, run

  `activate myenv`

* On macOS and Linux, in your Terminal Window, run

  `source activate myenv`

Conda prepends the path name`myenv`onto your system command.

## Jupyter Notebook

### Hotkeys

 Remember that to switch back and forth between `Command Mode` and `Edit Mode` with Esc and Enter

Shift+Enter: Runs the code or markdown on a cell

Up Arrow+Down Arrow: Toggle across cells

b: Create new cell

0+0: Reset Kernel

m: Convert cell to Markdown

y: Convert cell to Code

D+D: Delete the cell\(if it's not the only cell\) or delete the content of the cell and reset cell to Code\(if only one cell left\)

o: Toggle between hide or show output

Shift+Arrow up/Arrow down: Selects multiple cells. Once you have selected them you can operate on them like a batch \(run, copy, paste etc\).

Shift+M: Merge selected cells.

Shift+Tab: \[press these two buttons at the same time, once\] Tells you which parameters to pass on a function

Shift+Tab: \[press these two buttons at the same time, three times\] Gives additional information on the method

### Команды

**Cell Tricks**

 `?function-name`: Shows the definition and docstring for that function

 `??function-name`: Shows the source code for that function

 `doc(function-name)`: Shows the definition, docstring **and links to the documentation** of the function \(only works with fastai library imported\)

**Line Magics**

Line magics are functions that you can run on cells and take as an argument the rest of the line from where they are called. You call them by placing a '%' sign before the command. The most useful ones are:

`%matplotlib inline`: This command ensures that all matplotlib plots will be plotted in the output cell within the notebook and will be kept in the notebook when saved.

`%reload_ext autoreload`, `%autoreload 2`: Reload all modules before executing a new line. If a module is edited, it is not necessary to rerun the import commands, the modules will be reloaded automatically.

 `%timeit`: Runs a line ten thousand times and displays the average time it took to run it.

```text
%timeit [i+1 for i in range(1000)]
```

```text
54.4 µs ± 1.37 µs per loop (mean ± std. dev. of 7 runs, 10000 loops each)
```

 `%debug`: Allows to inspect a function which is showing an error using the [Python debugger](https://docs.python.org/3/library/pdb.html).

```text
for i in range(1000):
    a = i+1
    b = 'string'
    c = b+1
```

```text
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-14-8d78ff778454> in <module>()
      2     a = i+1
      3     b = 'string'
----> 4     c = b+1

TypeError: must be str, not int
```

