# Jupyter Notebook

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

## [Viewing a list of your environments](https://conda.io/docs/user-guide/tasks/manage-environments.html#id8)

To see a list of all of your environments, in your Terminal window or an Anaconda Prompt, run:

```
conda info --envs
```

## [Activating an environment](https://conda.io/docs/user-guide/tasks/manage-environments.html#id5)

To activate an environment:

* On Windows, in your Anaconda Prompt, run
  `activate myenv`
* On macOS and Linux, in your Terminal Window, run
  `source activate myenv`

Conda prepends the path name`myenv`onto your system command.

