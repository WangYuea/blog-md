---
title: vi编辑器
---
linux操作系统标配，相当于windows下的记事本。
### vi编辑器的三种模式
vi编辑器提供了3种模式，分别是命令模式、插入模式、底行模式，每种模式下用户所能进行的操作是不一样的。
### vi常用的操作
```bash
a) 打开/创建文件， vi 文件路径
b) 底行模式 :w保存，:w filenme另存为
c) 底行模式 :q退出
d) 底行模式 :wq保存并退出
e) 底行模式 :e! 撤销更改，返回到上一次保存的状态
f) 底行模式 :q! 不保存强制退出
g) 底行模式 :set nu 设置行号
h) 命令模式 ZZ（大写）保存并退出
i) 命令模式 u辙销操作，可多次使用
j) 命令模式 dd删除当前行
k) 命令模式 yy复制当前行
l) 命令模式 p 粘贴内容
m) 命令模式 ctrl+f向前翻页
n) 命令模式 ctrl+b向后翻页
o) 命令模式 i进入编辑模式，当前光标处插入
p) 命令模式 a进入编辑模式，当前光标后插入
q) 命令模式 A进入编辑模式，光标移动到行尾
r) 命令模式 o进入编辑模式，当前行下面插入新行
s) 命令模式 O进入编辑模式，当前行上面插入新行
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