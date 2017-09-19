---
title: git回滚
---
### git快照的回滚
#### git reset --hard
``` bash
1、回滚本地仓库的快照
2、使用本地仓库的快照覆盖暂存区
3、使用本地仓库的快照覆盖工作目录
```
不保存暂存区和工作目录的文件代码
#### git reset --soft
```bash
只回滚本地仓库的快照
```
暂存区和工作目录的不变
#### git reset --mixed（默认）
```bash
回滚本地仓库的快照并且覆盖暂存区，但是不覆盖工作目录
```
取消最后一次提交
####
git reset --hard 倒数第二个commitid
git reset --hard HEAD^
两者一样
HEAD便是本地仓库的最新快照
^表示上一次快照
### git add 的逆操作
直接操作：
```bash
git reset --mixed HEAD  mixed 可省略
git reset HEAD
git reset  最后一次的commitId
```
mixed回滚本地仓库的快照并且覆盖暂存区，但是不覆盖工作目录
### 回滚所有的修改操作
用暂存区覆盖工作目录
```bash
git checkout. （.代表全部修改）
git checkout 文件列表
```
### git rm --cached  文件列表
把暂存区的文件删除

