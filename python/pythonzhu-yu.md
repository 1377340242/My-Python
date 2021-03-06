#### 

> # Python总结

Python之父Guido van Rossum（吉多·范罗苏姆）荷兰计算机程序员。Python于1991年发行。

	Python程序可以分解成模块、语句、表达式以及对象如下所示。

\(1\)	程序由模块组成

\(2\)	模块由语句组成

\(3\)	语句由表达式组成

\(4\)	表达式建立并处理对象

	Python基本数据类型：数值、字符串、列表、元组、字典、集合。

	面向对象的三大基本特征：封装、继承、多态

### **Python专业术语**：

1.	类：封装对象属性和行为的载体，是具有相同属性和方法的对象的集合。

2.	多态：一个操作符的意义取决于被操作的对象。

3.	动态：对象的类型是在运行过程中自动决定的，而不是通过代码声明。

4.	语句：告诉程序要做哪些事情。

5.	序列：按一定顺序排列的存放多个值的连续内存空间。

6.	关键字参数：通过参数名进行匹配。

7.	位置参数：根据文字决定参数值。

8.	作用域：变量在程序中能够使用的位置。

9.	原地修改：能够在对象本身进行修改，而不产生其他对象。

10.	递归函数：直接或间接地调用自身以进行循环的函数。

11.	迭代协议：对象必须提供一个\_\_next\_\_方法，执行该方法要么返回迭代中的下一项，要么就引起一个StopIteration异常，以终止迭代

12.	生成器：生成器是支持迭代协议的对象：它们有\_\_next\_\_方法。可以在def函数中使用yield返回值、加圆括号的列表解析或在类中定义\_\_iter\_\_创建。

13.	迭代器：是一个可以记住遍历的位置的对象。

14.	可迭代对象：能够逐一返回其成员项的对象。

15.	命名空间：包含对象所有属性的一个字典，可用.\_\_dict\_\_方式获得。

### 注意：

1.	类型属于对象， 而不是变量。

2.	赋值运算是传递的对象引用。

3.	参数的传递实质是变量的幅值。

4.	函数传参注意事项：数量必须和定义时一致

5.	“\*”号在函数头部它意味着收集任意多的参数，而在调用者中意味着传递任意多的参数。

6.	Keyword-only参数： 参数必须按照名称传递，且必须在\*\*kwargs之前。

7.	模块中的顶层变量都会变成导入模块的属性，变量的导入实质是变量的复制而不是连接。

8.	def语句只执行def语句头，class语句运行会顶层语句。

9.	def语句表示定义一个函数并将函数赋值非变量（函数名），class语句同理。

10.	只有\_\_slots\_\_列表内的这些变量名可赋值为实例属性，且该实例没有\_\_dict\_\_属性。

11.	类中的\_\_\*形式的属性和方法，无论类还是实例都无法使用.\_\_\*方式访问。原因：Python将\_\_\*形式压缩为\_类名\_\_\*的形式，要想访问可是使用.\_类名\_\_\*方式访问。

12.	try语句块中发生错误后，finally语句执行后在抛出异常。

13.	raise空语句抛出最近异常。

### 1.1 模块

模块至少有三个角色：

1.	代码重用

2.	划分系统命名空间

3.	共享服务和数据

### 2.1 装饰器：返回一个可调用对象的可调用对象。

#### 2.1.1 类装饰器：主要用于装饰类，以管理类和类的实例对象

\(1\)	管理类的方法（类对象的扩展）：将类对象重新绑定到装饰器，并返回最初的类对象。

\(2\)	管理类实例对象的方法：在装饰器中插入一个包装器对象（在该包装器中创建类实例）。

#### 3.1 元类：创建一个类的类

         元类通常是type类的子类，它重新定义了类创建协议方法，以便定制在一条class语句的末尾发布的类创建调用；它通常会重定义\_\_new\_\_和\_\_init\_\_方法以接入类创建协议。

要管理类，装饰器直接扩展并返回最初的类对象。元类在创建一个类之后扩展它。

































