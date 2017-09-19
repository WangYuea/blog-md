---
title: git知识
---
### git的三个工作区域
``` bash
工作目录
暂存区域
本地仓库
```
### git管理文件的4中状态
```bash
未追踪untraced
已暂存staged
已提交commited
已修改modified
```
### git工作流程-本地创建仓库
1、配置用户信息
2、初始化仓库
3、添加文件到暂存区
4、提交文件
5、查看文件状态
6、查看提交历史
7、撤销文件修改
8、恢复版本
### git分支操作
#### 分支概述
#### 分支操作
1、创建分支
2、切换分支
3、合并分支
4、删除分支
### Git命令
配置用户信息

全局配置，软件安装目录C:\Program Files\Git\mingw64\etc\gitconfig
用户配置，用户名目录C:\Users\www.gitconfig
项目配置，项目目录
```bash
+ git config --global user.name zhangsan
+ git config --global user.email "zhangsan@163.com"
```
查看文件状态
```bash
+ git status
```
查看提交记录(按q键退出)
```bash
+ git log
```
工作区添加到暂存区
```bash
+ git add
```
暂存区覆盖工作区内容
```bash
+ git checkout
```
暂存区提交到本地仓库
```bash
+ git commit -m 'bug fixed'
```
回滚特定版本
```bash
+ git reset --hard <commit>
```