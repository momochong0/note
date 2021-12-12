创建项目+创建应用+安装应用+配置模板路径+本地化+mysql数据库+URLconf+视图
1、创建项目
在要创建项目的位置，输入：
django-admin startproject 项目名

然后cd 项目名,进入该目录
python manage.py runserver 0.0.0.0:8000
2、创建应用
python manage.py startapp 应用名
3、安装应用
    # 添加子应用    'book.apps.BookConfig' # 应用名+.apps.+应用名(首字母大写)Config
    # book #  或者直接用应用名，但直接用应用名，book.apps文件中其他配置则不会起作用

4、配置模板路径

5、本地化（如果不本地化，插入数据库时用的时间为协调世界时UTC）

    # 设置简体中文
    LANGUAGE_CODE = 'zh-Hans'
    # 亚洲上海时区
    TIME_ZONE = 'Asia/Shanghai'

6、配置数据库


在Django的工程同名子目录的__init__.py文件中添加如下语句

import pymysql

pymysql.install_as_MySQLdb()

修改DATABASES配置信息:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'HOST': '127.0.0.1',  # 数据库主机
        'PORT': 3306,  # 数据库端口
        'USER': 'root',  # 数据库用户名
        'PASSWORD': 'root',  # 数据库用户密码
        'NAME': 'book'  # 数据库名字
    }
}

在MySQL中创建数据库

create database book charset=utf8;


<!-- python manage.py migrate  # 创建一个配置文件中指定的数据库文件 -->

#  在应用中添加相应的表的定义
python manage.py makemigrations 应用名  # 生成该应用中相应的更新脚本

python manage.py migrate  # 根据上面更新的脚本，重新生成数据库文件

#  如果修改了数据库的表结构，如果是添加字段，注意字段的默认值（有个允许为空值的参数）,另外再次执行上面两行命令

python manage.py createsuperuser  # 创建管理员账号

#  将创建的表添加到后台管理界面中，便于维护
from django.contrib import admin

admin.site.register(Customer)

# 管理员后台运行（三步）
修改语言和时区
注册模型
添加模型的__str__方法

7、路由(URLconf)配置

8、视图