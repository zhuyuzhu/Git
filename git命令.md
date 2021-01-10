# GIt命令

**1、查看提交记录**

`git log`  查看提交记录

git 查看某个文件的提交记录：

> git log javascript.js

git 查看某个目录下已经删除的某个文件：

> git log -- ./javascript.js



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

