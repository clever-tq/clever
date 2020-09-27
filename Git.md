# Git



## 总结

* Git是分布式版本控制系统，它就没有中央服务器的，每个人的电脑就是一个完整的版本库，这样，工作的时候就不需要联网了，因为版本都是在自己的电脑上。
* git config
  * 查看配置信息  git cinfig --list
  * 配置用户信息
  * git config --global user.name "xxx"
  * git config --global user.email "xxx"
* 初始化本地仓库 git init  
* git add  
  * 将文件添加到暂存区(临时存放代码的位置)一般做完一部分添加一次
* git commit -m "abc"
  * 提交暂存区代码到本地仓库
* git status
  * 查看当前仓库中所有文件的状态
* git log
  * 查看提交历史版本

### 三个区域

* 工作目录:放置代码的项目根目录
  * 工作目录中新建的文件没有被git管理
* 暂存区:临时管理代码的区域
  * 只要代码添加到暂存区就被git管理起来
* 本地仓库:管理正式代码的版本信息
  * 阶段性完成的小功能可以提交到本地仓库

### 文件4个状态

- 未跟踪，新建的文件（红色的）
- 已暂存，添加到暂存区的文件（绿色的文件）
- 已提交，本地仓库中的文件
- 已修改，暂存区的代码被修改了（代码在工作目录）（红色的）

### 操作流程强化

* 添加到暂存区

  * git add .

  ```js
  //添加所有文件到暂存区
  git add .
  //添加指定文件到暂存区 
  git add a.txt b.txt
  //添加所有文件到暂存区
  git add *
  git add *.js
  
  ```

* 提交到本地仓库

  * 什么情况下需要commit？完成了一个阶段性任务
  * git commit -m 备注

  ```js
  //如何修改提交的最后一次备注
  git commit --amend
  #具体步骤
  #执行命令 git commit --amend
  #在打开窗口中按一下字符 a，那么进入编辑状态
  #此时就可以修改备注了，修改完成后按下Esc 退编辑
  #英文输入法状态下，按 shift + :  然后左下角出现光标
  # 输入wq，然后回车，完成编辑
  ```

* 提交代码时 不添加-m会强制提示窗口填写备注

* 提交代码是否先add在commit?

  * 如果有新的的文件 必须先add再commit

* 查看帮助文档的方式

  * git add --help
  * git commit --help

### 回滚(撤销)操作

* git add的逆操作 
  * 把暂存区中的文件移除到工作目录(这些被移除的文件不再被git管理，可以删除）

* git restore --staged a.js
* git rm --cached a.js
*  如果希望把文件从暂存区撤销到工作目录并且删除工作目录的文件，可以执行如下命令
  * git rm a.js
  * git rm -f a.js

### 撤销代码的修改

* 该命令执行时，一定要慎重的考虑好（撤销后，无法再找回）

* git checkout 

### 把本地仓库的代码撤销

* git reset --hard 615da1d 回滚到指定版本前
* 查看历史版本的简化方式
  * git log --oneline
* 用当前本地仓库的最新代码覆盖工作目录和暂存区
  * git reset --hard HEAD





## 问题

git rm a.js 用法 已解决

把本地仓库的代码撤销掉不是特别清晰 已解决

