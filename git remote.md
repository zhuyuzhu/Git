# 远程仓库

1、显示远程仓库

```shell
git remote -v
```



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



3、获取远程仓库的数据

```shell
git fetch [remote-name]
```



4、将数据推送到远程仓库中

```shell
git push [remote-name] [branch-name]
```



5、检查远程仓库

```shell
git remote show [remote-name]
```



6、删除和重命名远程仓库

```shell
git remote rename [remote-name] [new-remote-name]
```

```shell
git remote rm [remote-name]
```

我的理解：

添加名为origin的仓库，与对应地址的远程仓库连接

如果再添加origin名的仓库，与另一个远程地址连接，那么就报：fatal: remote origin already exists.

如果在名为origin的与仓库A连接，是否可以再添加origin1与仓库B连接呢？我觉得应该是可以的。

