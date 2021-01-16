# 远程仓库



2、添加远程仓库

```shell
git remote add pb https://github.com/zhuyuzhu/JavaScript.git
```

pb 为本地仓库的名字——简称

查看远程仓库时：

```shell
$ git remote -v
pb      https://github.com/zhuyuzhu/JavaScript.git (fetch)
pb      https://github.com/zhuyuzhu/JavaScript.git (push)

```

与之前的其他默认仓库对比：简称为origin

```shell
$ git remote -v
origin  https://github.com/zhuyuzhu/Git.git (fetch)
origin  https://github.com/zhuyuzhu/Git.git (push)

```

当向远程仓库push代码时：

```shell
$ git push pb master
```



