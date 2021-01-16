# Git入门——特点、文件状态、配置文件

### Git特点

1、版本控制；

2、分布式版本控制：

本地客户端是仓库的完整镜像，不管哪个服务器出现故障，都可以用本地的镜像来恢复服务器。每次操作都是对数据的一次完整备份。

3、快照而非差异：

Git抓取一张所有文件状态的快照，然后存储一个指向该快照的索引。出于效率的考虑，如果某些文件没有变动，Git不会重新保留这些文件，而是保持之前已保存过的相同文件的链接。Git就是一个微型文件系统。

4、几乎所有的操作都在本地；

5、Git在进行数据存储时，会对数据进行校验和计算，校验机制是SHA-1散列，由40个16进制数字组成（0~f），Git不是通过文件名进行数据保存，而是通过散列值进行数据保存。

6、Git只增加数据：

每次提交都是向Git提交了快照，基本上所有的操作都是向Git数据库中添加数据，所以很难让Git系统丢失数据。

### 文件三种状态

本地Git三种状态：

**工作目录（modified已修改）——暂存区（staged已暂存）——Git仓库（commited已提交）**

工作目录中是对文件进行修改，修改的文件都处于modified状态。当执行`git add` 时，将修改的文件添加到暂存区，当执行`git commit`时，将暂存的文件都提交到Git仓库中。

我们可以多次`git add`，将文件多次添加到暂存区，当我们执行`git commit`时，将暂存区的所有文件提交到Git仓库中。

（1）工作目录中，对文件进行修改时

`git status` 查看文件状态：

> Changes not staged for commit: ——未进入暂存区的改变  或者 Untracked files: 未跟踪的文件
>
> modified:   "input\346\240\207\347\255\276.md"——文件状态modified

（2）暂存区，由git add命令将文件添加到暂存区

> Changes to be committed: ——要被提交的改变，说明在暂存区
>
>  modified:   "input\346\240\207\347\255\276.md"

（3）Git仓库

> git commit 将文件提交的Git仓库中

需要注意的是：暂存区保存的是git快照，如果某个文件已经在暂存区，此时对文件再进行修改，那么这个文件会有两个状态，一个是处于暂存区的状态，还是之前文件内容；一个是处于修改状态，是文件最新内容。如果此时执行git commit，只会将处于暂存区的内容提交到Git仓库。

git命令快照会对文件内容进行保存，git commit只会将暂存区的内容提交到Git仓库中。

（4）git push命令

将本地Git仓库的文件推到远程仓库中。所以可以多次提交文件到Git仓库中，最近再进行一次git push操作，将Git仓库的内容推到远程仓库中。

Git配置——git config

一次配置，永久生效。

### git config来获取和设置变量。

**1、git配置存在于三个地方：**

（1）`/etc/gitconfig`文件：包含了系统中所有用户及其仓库的值。如果使用`git config --system`选项，那么就会操作该文件中的git配置变量。

（2）`~/.gitconfif `或 `~/.config/git/config` 文件：针对的是自己，可以通过 `git config --global`选项，从该文件中读写git配置变量。

（3）当前仓库Git目录（`.git/config`)中的config文件，针对单个仓库。使用`git config`选项。

每一级都会覆盖上一级中的设置，所以.git/config 中的配置要优先于 /etc/gitconfig中的值。在windows系统中，Git会在$HOME目录中查找.gitconfig文件，也查找/etc/gitconfig，不过这是相对于MSys的根目录，该目录是在安装程序时选择的安装目录。

**2、--list选项来查看当前Git的所有配置**

（1）查看当前目录的Git配置：

> $ git config --list
>
> http.sslcainfo=D:/Git/mingw64/ssl/certs/ca-bundle.crt
> http.sslbackend=openssl
> diff.astextplain.textconv=astextplain
> core.autocrlf=true
> core.fscache=true
> core.symlinks=false
> user.name=zhuyuzhu
> user.email=struggle_zhu@163.com
> credential.helper=store
> core.repositoryformatversion=0
> core.filemode=false
> core.bare=false
> core.logallrefupdates=true
> core.symlinks=false
> core.ignorecase=true
> remote.origin.url=https://github.com/zhuyuzhu/CSS.git
> remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*

（2）查看全局Git的配置：

> $ git config --global --list
>
> user.name=zhuyuzhu
> user.email=struggle_zhu@163.com
> credential.helper=store

（3）查看系统Git的配置：

> $ git config --system --list
>
> http.sslcainfo=D:/Git/mingw64/ssl/certs/ca-bundle.crt
> http.sslbackend=openssl
> diff.astextplain.textconv=astextplain
> core.autocrlf=true
> core.fscache=true
> core.symlinks=false

**3、获取或设置某个配置项**

使用git config --list 获取当前配置文件下的所有配置后，可以对每项配置文件单独获取或者设置

比如：

> $ git config user.name 'zhuzixi' //重新设置名字
>
> $ git config user.name //查看名字是否设置成功
> zhuzixi

主要有以下几个方向的配置：

用户信息的配置：

> user.name
>
> user.email

域的配置：

> core.autocrlf=true
> core.fscache=true
> core.symlinks=false
>
> core.repositoryformatversion=0
> core.filemode=false
> core.bare=false
> core.logallrefupdates=true
> core.symlinks=false
> core.ignorecase=true

远程仓库的配置：

> remote.origin.url
>
> remote.origin.fecth



### git提示信息

1、Everything up-to-date

git push时，提示该词，意思是：本地所有最新的，没有要push到远程仓库的。



### 获取帮助

git help <verb>

git <verb> --help

比如：

git config --help

默认浏览器会打开该地址：file:///D:/Git/mingw64/share/doc/git-doc/git-config.html

