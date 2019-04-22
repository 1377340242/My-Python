### 安装：

pymsql安装：

$ pip install pymysql

mysql官网：[https://dev.mysql.com/doc/refman/8.0/en/](https://dev.mysql.com/doc/refman/8.0/en/)

mysql安装：[https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/)

**注意：添加系统变量到配path。**

教程：[https://pymysql.readthedocs.io/en/latest/index.html](https://pymysql.readthedocs.io/en/latest/index.html)

### 启动：

管理员权限启动CMD：$  net start mysql

进入mysql shell方法：$  mysql -u root -p

#### 退出：$ quit

#### 数据类型的选择方法和技巧：

* 不需要保存小数时，使用整数类型
* 小数精度要求较高时或者需要进行数值运算时，使用DECIMAL类型
* 存储较大范围的日期时用datatime，否则则，尽量使用TIMESTAMP，因为默认的情况下，当插入一条记录但并没 有指定TIMESTAMP这个列值时，MySQL会把TIMESTAMP列设为当前的时间。
* 如果对速度有较高要求时，可使用可以使用CHAR类型，反之可以使用 VARCHAR类型来实现。
* BLOB主 要存储图片、音频信息等，而TEXT只能存储纯文本文件。

* 在需要从多个值中选取**一个**时，可以使用ENUM；在需要取**多个**值的时候，适合使用SET类型，

### 建立主键和外键时需要注意的事项：

* 主键中的值必须唯一
* 建立外键时的四种动作

cascade：主表删除或更新相应的数据行，则子表同时删除或更新与主表相匹配的行，即级联删除、更新。

set null：主表删除或更新相应的数据和，则子表同时将与主表相匹配的行的外键列置为null。当外键列被设置为not null时无效。

no action：数据库拒绝删除或更新主表。

restrict：数据库拒绝删除或更新主表。如果未指定on delete或on update的动作，则on delete或on update的默认动作就为restrict。

**注意事项：设置外键的表称为子表，外键参考的表为父表**

