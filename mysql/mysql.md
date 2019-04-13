# 1.连接mysql数据库：

```py
import pymysql
config = {
    'host': 'localhost',
    'user': 'root',
	'database':'db',
	'port':3306,
    'password': 'root',
    'charset': 'utf8'
}
db = pymysql.connect(**config)  #连接数据库
print(type(db))#返回的是<class 'pymysql.connections.Connection'>Connection类。
print(db.open)#如果连接打开，则返回True
print(db.ping())#检查服务器是否处于活动状态，活动时返回None，否则，返回错误
```

## 2.创建游标对象cursor：

> 游标对象主要是用于和数据库进行交互。

```
cursor=db.cursor()#创建游标对象
```

```
主要函数：
cursor.execute(sql,args)#用于执行SQL语句,args的类型为list、元组和字典
        >If args is a list or tuple, %s can be used as a placeholder in the query.
        >If args is a dict, %(name)s can be used as a placeholder in the query.
cursor.fectchone()#获取下一行
cursor.fetchmany（size = None)#获取多行数据，通过size设定。
cursor.fetchall（）#获取所有行。
cursor.executemany(sql,args)#批量执行SQL语句,实际上该函数是遍历args然后将每个参数传递给cursor.execute(sql,args)
重复执行cursor.execute(sql,args)函数。
```

### 3.



