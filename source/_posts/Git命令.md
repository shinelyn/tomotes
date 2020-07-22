---
title: Git常用命令
date: 2018-11-24
tags: 
---



##### Git 命令清单
- Workspace：工作区
- Index / Stage: 暂存去
- Repository：仓库区
- Remote: 远程仓库
<!--MORE-->

#### 一，新建代码块
- 在当前目录下新建一个 Git 代码块， `$ git init`

- 新建一个目录，将其初始化为Git代码库 `$ git init [project-name]`

- 下载一个项目和它的整个代码历史 `$ git clone `

#### 二，配置
- 显示当前的git配置  `git config --list`
- 修改当前的git 配置  `git config -e [--globle]`
- 提交代码时的用户信息 

```
git config [--global] user.name "[name]" 
git config [--global] user.email "[email address]" 
```
#### 三，添加和删除文件
- 