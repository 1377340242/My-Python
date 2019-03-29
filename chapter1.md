> # BeautifulSoup库
>
> ## 有关BeautifulSoup库的安装、文档及用法
>
> ### **BeautifulSoup库的安装：**

```py
pip install BeautifulSoup
```

### **BeautifulSoup库的中文文档：**[**https://beautifulsoup.readthedocs.io/zh\_CN/v4.4.0/**](https://beautifulsoup.readthedocs.io/zh_CN/v4.4.0/)

```
html_doc = """
<html><head><title>The Dormouse's story</title></head>
<body>
<p class="title"><b>The Dormouse's story</b></p>
<p class="story">Once upon a time there were three little sisters; and their names were
<a href="http://example.com/elsie" class="sister" id="link1">Elsie</a>,
<a href="http://example.com/lacie" class="sister" id="link2">Lacie</a> and
<a href="http://example.com/tillie" class="sister" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>
<p class="story">...</p>
"""
```

1.首先建立soup对象：

```py
from bs4 import BeautifulSoup   #导入模块
soup = BeautifulSoup(html_doc, 'html.parser')#将HTML网页字符内容传入BeautifulSoup
#soup实质也是一个tag标签
print(soup.prettiry())
# <html>
#  <head>
#   <title>
#    The Dormouse's story
#   </title>
#  </head>
#  <body>
#   <p class="title">
#    <b>
#     The Dormouse's story
#    </b>
#   </p>
#   <p class="story">
#    Once upon a time there were three little sisters; and their names were
#    <a class="sister" href="http://example.com/elsie" id="link1">
#     Elsie
#    </a>
#    ,
#    <a class="sister" href="http://example.com/lacie" id="link2">
#     Lacie
#    </a>
#    and
#    <a class="sister" href="http://example.com/tillie" id="link2">
#     Tillie
#    </a>
#    ; and they lived at the bottom of a well.
#   </p>
#   <p class="story">
#    ...
#   </p>
#  </body>
# </html>
```

2.BeautifulSoup的简单应用

```
soup.title
#<title>The Dormouse's story</title>

print(soup.head)
#<head><title>The Dormouse's story</title></head>

print(soup.a.name)#打印a标签的名字》》只打印第一个a标签
#a

print(soup.a.string)#打印a标签的字符串>>>这里只打印第一个a标签的字符串
#Elsie

print(soup.p['class'])#第一个p标签的class属性的值
# ['title']
print(soup.get_text())#从文档中获取所有文字内容:
'''The Dormouse's story
The Dormouse's story
Once upon a time there were three little sisters; and their names were
Elsie,
Lacie and
Tillie;
and they lived at the bottom of a well.
...
```

```
2.BeautifulSoup的find和find_all方法：
```

```
1.find方法
p=soup.find('p')#查找第一个p标签，返回的是一个tag对象
#<class 'bs4.element.Tag'>
#<p class="title"><b>The Dormouse's story</b></p>
2.find_all方法：
a=soup.find_all('a')#查找所有a标签，返回的是所有a标签组成的列表
#[<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>, <a class="sister" href="http://example.com/lacie" id="link2">Lacie</a>, <a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>]
```

3..content方法：可以将tag的子节点以列表的方式输出

```
print(soup.body.contents)
'''['\n', <p class="title"><b>The Dormouse's story</b></p>, '\n', <p class="story">Once upon a time there were three little sisters; and their names were
<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>,
<a class="sister" href="http://example.com/lacie" id="link2">Lacie</a> and
<a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>, '\n', <p class="story">...</p>, '\n']'''
```

4.通过tag的`.children`生成器,可以对tag的子节点进行循环:

`print(soup.body.children)#返回的是一个列表生成器`

`#<list_iterator object at 0x000002152A1C6940>`

5..descendants访问tag的所有子孙节点

```
descendants=soup.body.descendants
for child in descendants:
    print(child)
#返回所有子节点，孙节点，还包括了节点中的字符串
```

6.string对象

```
#string对象仅会返回一个标签的字符串，且当一个标签有子节点是就会返回None
print(soup.p.string)
#The Dormouse's story
print(soup.html.string)
#None
```

7..strings 和 stripped\_strings

.strings返回标签的多个字符串生成器，其中可能包含空格

```
print(soup.html.strings)
#<generator object _all_strings at 0x000001803E7E9048>
```

.strpped\_srings返回不含空格的对个字符串列表

```
print(soup.html.stripped_strings)#不含空格
#<generator object stripped_strings at 0x000001501D909048>
```

8..parent:tag的父节点

```
print(soup.a.parent)
#<p class="story">Once upon a time there were three little sisters; and their names were
<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>,
<a class="sister" href="http://example.com/lacie" id="link2">Lacie</a> and
<a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>;
and they lived at the bottom of a well.</p>
```

9.遍历整个HTML树的集中方式：

* 使用find\_all\(\)方法，其中limit参数表示限定查找的个数，如果只想搜索tag的直接子节点,可以使用参数`recursive=False`

```
find_all('a')#使用标签名搜索
find_all('p',class_='title)#使用标签和属性进行精确搜索
find_all('^<a')#使用正则表达式进行模糊搜索
find_all(['a','b'])#使用列表进行搜索，如果传入列表参数,Beautiful Soup会将与列表中任一元素匹配的内容返回.
find_ALL(True) 可以匹配任何值,下面代码查找到所有的tag,但是不会返回字符串节点
#还可以自定义函数来进行搜索：
#该函数的意思是tag包含class属性而不包含id属性，
def find_tag(tag):
 return tag.has_attr('class') and not tag.has_attr('id')
使用find_all(find_tag)调用
```

10.CSS选择器

```
#使用标签的方式
soup.select("title")
# [<title>The Dormouse's story</title>]
#通过tag的id查找:
soup.select("#link1")--》soup.select("#link1,#link2")
# [<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>]
通过属性的值来查找:
soup.select('a[href="http://example.com/elsie"]')#完整的属性值
# [<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>]

soup.select('a[href^="http://example.com/"]')#开头等于"http://example.com/"的所有标签
# [<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>,
#  <a class="sister" href="http://example.com/lacie" id="link2">Lacie</a>,
#  <a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>]

soup.select('a[href$="tillie"]')#结尾为tillie的标签
# [<a class="sister" href="http://example.com/tillie" id="link3">Tillie</a>]

soup.select('a[href*=".com/el"]')#包含.com/el的标签
# [<a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>]

soup.select_one(".sister")#返回查找到的元素的第一个
# <a class="sister" href="http://example.com/elsie" id="link1">Elsie</a>
```

11.输出

* `str()`方法返回UTF-8编码的字符串,可以指定[编码](https://beautifulsoup.readthedocs.io/zh_CN/v4.4.0/#id55)的设置.

* 调用`encode()`方法获得字节码或调用`decode()`方法获得Unicode.

* 用`get_text()`方法获取到tag中所有子孙tag中的内容,并将结果作为Unicode字符串返回:

* ```
  soup.get_text("|", strip=True)#去除获得文本内容的前后空白:
  #u'I linked to|example.com'
  ```
* 


