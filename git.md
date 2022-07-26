# 常用 #：git BashHere  打开git

`命令`
 git --version  查看当前git版本
 工作流程  
git库      用于存放提交记录
暂存区     临时存放被修改的文件 
工作目录   被git管理的项目目录
git使用前的配置
配置提交人 git config --global user.name 提交人 姓名 
配置提交人 git config --global user.email  提交人邮箱
查看git 配置信息 git config --list  （--后没空格）
提交步骤
1 git init 初始化git仓库
2git status 查看文件状态
3 git add 追踪想要管理的文件
4 git commit -m 提交文件 -m 后面加上提交说明  
5 git log 查看提交记录  
6.git rm --cached 文件 将文件从暂存区中删除
7.git checkout 暂存区中的文件 覆盖工作目录中的文件 工作目录还存在
8.git reset --hard commintID 工作目录 喝暂存区都有问题  后面的提交也没了

# 分支 # 
1.master 主分支    自动产生 
2.develop 开发分支（类副本） 基于master分支创建
3.feature 功能分支  基于开发分支创建的
2.2
1 git branch  查看分支
2 git branch 分支名称（develop feature） 创建分支
3 git checkout 分支名称  切换前 需要先提交 
开发分支上的不应出现在 主分支上 
4.git merge 来源分支  合并分支  （merge后面的被合并 ）
5 git branch -d 分支名称（-D强制删除）删除分支 合并后才允许被删除   防误删

2.3 暂时保存改变
git stash 存储临时改动
git stash pop 恢复改动 


## 基本上传 操作 （不管分支 ##）
1 git init 初始化
2 添加文件 git status 查看 
3 git add 添加到 临时文件
4 git commit -m 提交到仓库
5 git log 查看提交记录

## git恢复到暂存区状态 ##
1 git status  查看 
2 git add 添加到暂存区  
3 git checkout 文件名 （在暂存区中 ）  恢复 


## git 删除（暂存区） ##
1 git status  查看 
2 git add 添加到暂存区   
3 git rm --cached 暂存区中删除


 git 恢复到某个状态版本（git 和工作代码存在问题）
1 git status 查看
2 git commit -m 提交到仓库
3 git log 查找不同次数提交的的commit 
4 git reset --hard  恢复到那个状态 


# git 分支操作 #
 
## git 创建分支 ##
1.git  branch 查看分支
2.git branch test (加上名字) 在主分支下创建默认
3.可以在该分支下进行操作任何东西比如创建html css 等

## git 切换分支 ##
1.git branch 查看分支
2.git branch name 创建分支 （如果有了 可以省略） 
3.git checkout name 切换到 name 这个分支
4.可以在该分支下进行操作任何东西比如创建html css 等
5. git commit-m 提交上去 就不会有跟随 
6. 

 ## git 合并分支  ##
1.git branch 查看
2. git checkout master (or被合并的上级分支)
3. git merge 被合并的分支 
4. PS：合并完 被合并分支还存在 可以继续开发

# #git 删除分支 ##
1.git branch 查看
2.git merge 合并分支先
3.git branch -d  删除分支 （要在上级分支删除 不能在本分支删除自己）
4. （
5. git checkout 分支
6. git add 提交一个文件
7. git commit-m 提交上去 
8. git checkout master 
9. git branch -D 强制删除分支
10. ）

 ##git push 推送远程仓库## 
第一次提交需要用户名账号密码 第二次 不需要输入 win10 自动保存了
origin 别名 为 仓库别名 可以自定义 

方法1 git push  仓库地址名  分支名称 推送到远程仓库  A推送到远程 
方法2 
1.写别名 git remote add  origin(别名) 仓库地址 
2. 推送 git push origin(别名)  master 
方法三
1.写别名 git remote add  origin(别名) 仓库地址 
2. 推送 git push -u  origin(别名)  master  只需要一次-u 就不需要输入别名+分支

## git clone 克隆仓库  ##
首次开发使用为主

克隆 很全面  包括别名等 
1.git clone 仓库地址 无需身份验证
2.cd 文件夹名字
后续操作与其他相同
3.无法提交代码 没有权限
权限设置
1.Settings Collaborators
2. Add people
3. 其他人的github账号
4.Copu invite link 复制邀请链接 B在登录的情况下 访问邀请链接并接受


# git pull 拉取 #
拉取最新版本
git pull 别名（远程仓库地址） 分支  
后期常用



# 默认分支修改（默认分支为非 master的情况下） #
1.点击Code行最后一个Settings
2.Settings下点击 Branches
3.中心区域🖊后面的logo
4.下拉菜单中选中想要的主分支
5.Update 更新
6.弹出   I understand, update the default branch. 单击即可
  
##解决冲突##
1.A推送 
2.B推送
都上传到远程仓库
B推送失败
!
操作
先拉取A的	conflict冲突
删除head 分割线 及结束部分 删除 重新保存并推送 解决冲突 修改不删除可以都存在

##  向其他库提交代码 ##
1.Fork   一下仓库 
2.clone 到本地
3.cd 切换到文件夹下
4.在本地对源码进行修改 
5.重新推送上自己的远程仓库
6. 单击pull request
7. create request 与原作者进行对话
8. 原作者pull requests 能看到修改的内容 可以进行对话
9. Commits 可以看代码
10. FilesChange可以看代码变化
11. merge pull request合并代码	


## ssh免登录 ##
1.生成密钥 ssh-keygen
目录 C盘下的用户中.ssh中
2.ssh 远程推送 
3.改别名 git remote add (origin_ssh)别名 远程库
4.git push 别名 分支
5.输入yes

## git忽略清单文件 ##
创建 .gitignore 不想管理的文件写里面

1.git add . |全部添加

## 为仓库写详细说明##
创建readme.md





# PS: #
 1 file changed,（几个文件有变化）
 24 insertions(+) （插入了多少行）
commit ff49d2fb351a0fa41e07aa738bdc0e07c37b279b (HEAD -> master) 提交ID 唯一标识
Author: phj <1771034478@qq.com> 提交人信息
nothing to commit, working tree clean 工作目录和暂存区都没有要提交的文件 工作目录是很干净的

删除分支不能在当前分支删除当前的分支 （不能“杀”自己）
Saved working directory and index state WIP on develop: ff49d2f demo第一次提交 暂时保存成了 可以切换分支 

win10 控制面板 中 所有控制面板选项 找到 凭据管理器 下的Windows凭据 就可以查看github（or gitee）密码 删除需要重新输入 
















