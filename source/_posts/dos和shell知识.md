---
title: dos 和 shell 知识
---
了解下dos和shell的知识，以及区别等。
### shell
shell是一个命令解释器(也是一种应用程序)，处于内核和用户之间，负责把用户的指令传递给内核并且把执行结果回显给用户，同时，shell也可以作为一门强大的编程语言。在linux/unix平台上，shell多半默认为Bash shell。
### dos
DOS是一种操作系统，出生在win之前，现在win上的那个命令行窗口叫做CMD。只是一个软件，运行的规则，脚本是批处理，但语法不完整。逻辑有缺陷，对win来说，这个大部分情况下不会用到，少数情况下会用，属于那种不能丢，但不丢也不会让你很痛苦的那种。但shell的脚本十分完整，逻辑也严谨。
### 两者的差异
1、shell区分大小写，DOS不区分大小写；
2、一般而言，shell的命令的开关可以简写（比如说“-a -l“可以简写为“-al“），而DOS的则不允许；
3、在脚本编写上的语法差别极大，比如说：两者的流程控制语句语法不同，变量的语法不同等；
4、shell可以在UNIX、GNU/Linux和Win下（cygwin bash shell）工作，DOS则还没有听说过能在Win/DOS以外的系统中工作；
5、shell原生支持正则表达式，DOS则不是。
### 常用的命令
``` bash
pwd (Print Working Directory) 查看当前目录
cd (Change Directory) 切换目录，如 cd /etc
ls (List) 查看当前目录下内容，如 ls -al
mkdir (Make Directory) 创建目录，如 mkdir blog
touch 创建文件，如 touch index.html
cat 查看文件全部内容，如 cat index.html
less 查看文件，如more /etc/passwd、less /etc/passwd
rm (remove) 删除文件，如 rm index.html、rm -rf blog
rmdir (Remove Directory) 删除文件夹，只能删除空文件夹，不常用
mv (move) 移动文件或重命名，如 mv index.html ./demo/index.html
cp (copy) 复制文件，cp index.html ./demo/index.html
tab 自动补全，连按两次会将所有匹配内容显示出来
> 和 >>重定向，如echo hello world! > README.md，>覆盖 >>追加
| 管道符可以将多个命令连接使用，上一次（命令）的执行结果当成下一次（命令）的参数。
grep 匹配内容，一般结合管道符使用

```