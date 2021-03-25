1、warning: LF will be replaced by CRLF in demo/dist/main.js.
The file will have its original line endings in your working directory

原因：存在符号转义问题

windows中的换行符为 CRLF， 而在linux下的换行符为LF，所以在执行add . 时出现提示，解决办法：

git config --global core.autocrlf false
