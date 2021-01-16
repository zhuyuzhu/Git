# git本地仓库和远程仓库冲突

Merge branch 'master' of https://github.com/zhuyuzhu/CSS

合并https://github.com/zhuyuzhu/CSS的“master”分支

Please enter a commit message to explain why this merge is necessary,

请输入一个提交消息来解释为什么这个合并是必要的，

especially if it merges an updated upstream into a topic branch.

特别是当它将更新的上游合并到主题分支时。

Lines starting with '#' will be ignored, and an empty message aborts the commit.

以'#'开头的行将被忽略，并且一条空消息将中止提交。



Type  :qa!  and press <Enter> to abandon all changes and exit Vim

Esc按钮退出insert模式，进入命令模式

:qa!  并按<Enter>放弃所有更改，退出Vim

:wq 并按Enter 保存更改，退出Vim



1、GitHub上每个文件的时间是提交时间，即本地仓库git commit的时间，而不是git push origin master的push到GitHub的时间。

2、GitHub上每个文件的提交备注，点击时候，可以显示该提交记录中，所有的提交文件。

### 没有文件冲突的本地仓库和远程仓库冲突——解决版本

（1）远程仓库上已经有其他开发者提交了文件，对远程仓库进行了改动

（2）本地仓库在未更新前，进行本地提交文件

那么本地肯定是无法push 到remote的，需要拉取远程

执行命令：

>  （1）git pull origin master
>
> Merge made by the 'recursive' strategy.
>
> 通过“递归”策略进行合并。
>
> 解释：拉取远程代码时，会自动和本地的进行合并
>
> 还需要输入信息，解释此次合并。——后面会看到此处的作用
>
> （2）git branch -a
>
> *master——主分支，已经合并了代码
> remotes/origin/master——临时分支，远程仓库的代码
>
> 查看分支，会生成一个临时分支
>
> （3）git push origin master
>
> 将仓库内容提交到远程仓库——实际上本地仓库已经有了远程仓库的所有提交记录和数据信息。本地不管进行多少次的git commit操作，都是可以的。
>
> 
>
> （4）git log
>
> 当进行log查看时，最近一次的log就是上面合并代码时的log。



### 有文件冲突的本地仓库和远程仓库冲突

