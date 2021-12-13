————————————————————git本机操作——————————————————————
1、创建test文件夹
2、进入test文件夹，并创建本地仓库.git
cd test
git init

3、配置个人信息
git config user.name 'momochong0'
git config user.email 'momochong0@163.com'

4、新建git.md文件
5、查看文件状态
git status
6、将文件添加到暂存区
git add . # 添加文件夹下所有未跟踪文件
或者git add git.md # 添加指定文件

7、将暂存区文件提交到仓库区
git commit -m '文件描述'

# 如果把-m 换成 -am ，代码将add和commit 操作合并

8、编辑文件，然后用add和commit反复提交


————————————————————git回退操作——————————————————————
1、仓库区回退
方法1:
git reset --hard HEAD~1

    HEAD表示当前最新版本
    HEAD^表示当前最新版本的前一个版本(windows需要其他参数)
    HEAD^^表示当前最新版本的前两个版本，以此类推...(windows需要其他参数)
    HEAD~1表示当前最新版本的前一个版本
    HEAD~10表示当前最新版本的前10个版本，以此类推...

方法2:
git reset --hard 版本号


2、撤销工作区代码
git checkout 文件名

3、将暂存区代码撤销到工作区
git reset HEAD  文件名
# 如果想继续撤销工作区代码，执行撤销工作区代码：git checkout 文件名 即可


# 多人协作

要同步服务器代码就执行：git pull
本地仓库记录版本就执行：git commit -am '版本描述'
推送代码到服务器就执行：git push

# 编辑代码前要先pull，编辑完再commit，最后推送是push

# 解决冲突

原则：谁冲突谁解决，并且一定要协商解决
方案：保留所有代码 或者 保留某一人代码
解决完冲突代码后，依然需要add、commit、push

# 标签

## 在本地打标签

 git tag -a 标签名 -m '标签描述'
 例：
 git tag -a v1.0 -m 'version 1.0'

## 推送标签到远程仓库

 git push origin 标签名
 例：
 git push origin v1.0

## 删除本地标签
  git tag -d 标签名
## 删除远程仓库标签
  git push origin --delete tag 标签名

# 分支

## 查看分支

  git branch

## 创建并切换到dev分支

 git checkout -b dev # 不加-b为切换分支

## 将分支推送到远程

 git push -u origin dev
或者执行如下语句：
 git push --set-upstream origin dev

## dev分支合并到master分支

### 先切换到master分支

git checkout master

### dev分支合并到master分支

  git merge dev

合并分支默认在本地完成，合并后直接推送即可

git push