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

