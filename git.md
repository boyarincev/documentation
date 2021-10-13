# GIT

Посмотреть содержимое stash

```
git show stash{0}
```

Посмотреть, что было сделано в старом коммите

```
git difftool {commit} {commit}
```

Список веток, в которых есть коммиты не вмерженные в master

```
git branch --no-merged master
```

Список коммитов, которые не вмержены в master

```
git cherry -v master <branch>
```

PUSH локальной ветки в удаленную:

```
git push <remote-name> <local-branch-name>:<remote-branch-name>
```

[полный ответ на stackoverflow](https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch)

Посмотреть blame в gui

```
git gui blame Makefile //Нужно указывать полный путь до файла, полный путь можно скопировать в git-gui
git gui browser maint //Показывает дерево файлов и папок проекта в котором можно выбрать любой файл 
//и откроется blame для него в отдельном окне
```

[https://git-scm.com/docs/git-gui/1.5.6](https://git-scm.com/docs/git-gui/1.5.6)

Статья с описанием разных стратегий Мержа

[https://habr.com/ru/post/195674/](https://habr.com/ru/post/195674/)
