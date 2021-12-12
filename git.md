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

8、编辑文件，然后用add和commit反复提交


————————————————————git回退操作——————————————————————
方法1:
git reset --hard HEAD~1

    HEAD表示当前最新版本
    HEAD^表示当前最新版本的前一个版本(windows需要其他参数)
    HEAD^^表示当前最新版本的前两个版本，以此类推...(windows需要其他参数)
    HEAD~1表示当前最新版本的前一个版本
    HEAD~10表示当前最新版本的前10个版本，以此类推...

方法2:
git reset --hard 版本号