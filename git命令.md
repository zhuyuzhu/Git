# GIt命令

**1、查看提交记录**

`git log`  查看提交记录

git 查看某个文件的提交记录：

> git log javascript.js

git 查看某个目录下已经删除的某个文件：

> git log -- ./javascript.js



查看3条日志：

> git log -3



以下说明了，本地HEAD->master在哪个commit，远程origin/master在哪个commit位置；

```shell
$ git log
commit 1943b76c7656e04ff8e922c135f1694e6f3224cf (HEAD -> master)
Author: zhuyuzhu <struggle_zhu@163.com>
Date:   Tue Mar 23 10:45:28 2021 +0800

    完善脚本

commit 405cad99278159fe04d490b5b23e81435eddc9bd (origin/master)
Author: zhuyuzhu <struggle_zhu@163.com>
Date:   Wed Feb 24 11:17:22 2021 +0800

    find hanzi
```



**2、显示某次提交**

`git show commitId`  查看某个提交记录

`git show commitId 文件` 查看某次提交记录中某个文件

`git show commitid -- 已删除的文件` 查看某个提交记录中已经删除的文件

> git show 675a793c5def12d337a59abbb66ab64a5819be5e -- javascript.js

git  输出某次提交版本中的某个文件到指定目录中

```git
git show commitId:文件路径 > 输出文件名

比如：将当前目录下的JavaScript.js 输出到当前目录且重命名为1.js

git show 97c119b73b880a1c8a5124c6a2f04f4bd7d113b4:./javascript.js > 1.js
```

git status



3、git add

```shell
git add <file>

git add . 

git add *
```





4、git commit

```shell
git commit -m

git commit -a -m  直接提交已经跟踪的修改文件
```



5、撤销操作

```shell
(use "git restore --staged <file>..." to unstage)

(use "git restore <file>..." to discard changes in working directory)
(使用“git restore <file>…”来丢弃工作目录中的更改)


```

6、删除文件

git rm 文件名：删除文件，该文件的状态直接进入暂存区，等待commit。

如果手动删除文件，该文件状态为Changes not staged for commit。修改了但是还未暂存，标示为deleted，而非modified。需要git add 才能进去到暂存区。

