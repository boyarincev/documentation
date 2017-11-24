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



