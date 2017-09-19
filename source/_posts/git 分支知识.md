---
title: git分支知识
---
默认只有一个分支，master默认为主分支
分支可以理解为代码的拷贝、副本
### git分支的一些命令代码
``` bash
查看分支：git branch -a(所有分支) -r(远程分支) 默认不写是本地分支
创建分支：git branch 分支名称  （参考当前分支创建的）
切换分支：git checkout 分支名称
合并分支：git merge 分支名称（来源分支） 从当前分支执行，来源分支合并到当前分支
例如在master下执行 git merge hello 把hello分支合并到master分支
删除分支： git branch -d  分支名称  必须把分支合并后才能删除，否则删除不了
git branch -D 分支名称 强制删除分支
创建并切换分支: git checkout -b 分支名称

```