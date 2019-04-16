## 安装库：

pip install jieba

pip install wordcloud

### jieba的使用方法：

```py
import jieba
seg_list = jieba.cut("我来到北京清华大学",cut_all=True)
#cut_all为True时为全模式，默认为False精确模式（效果要好一点）
#seg_list为一个生成器
#'/'.join(seg_list)#转化为字符串>>>'我/来到/北京/清华/清华大学/华大/大学'
#list(seg_list)转化为列表>>>['我', '来到', '北京', '清华', '清华大学', '华大', '大学']
seg_list = jieba.cut_for_search("小明硕士毕业于中国科学院计算所，后在日本京都大学深造") #搜索引擎模式
list(seg_list)#效果最好
[小明, 硕士, 毕业, 于, 中国, 科学, 学院, 科学院, 中国科学院, 计算, 计算所, 后, 在, 日本, 京都, 大学, 日本京都大学, 深造]
```

### WordCloud的用法：

**参数：**

* font\_path：展示的字体&gt;&gt;&gt;'字体.tff'
* width：画布的宽度px
* height：画布的高度px
* prefer\_horizontal:词水平排版的比率，默认0.9
* mask:array数组or None，遮罩绘制词云，图片的背景颜色要为白色，词云不在白色区域上绘制。
* scale:画布缩放比率，默认为1.0
* min\__font\__size:最小字体的大小，默认为4
* max\_words：要显示的词的最大个数，默认为200
* stopwords：string or None集合，设置需要屏蔽的词，
* backgroud\_color：背景颜色
* font\_step：字体步长，默认为1
* max\_font-size:最大字体，int or None，默认为None
* mode：string，默认为'RGB'
* colormap：字体颜色map，默认为’viridis‘，可以为matplotlib color map

方法：

generate\(text\)\#根据文本生成词云

generate\__from\_text_\(text\)\#实际上generate（text）就是调用的该函数

to\_file\(filename\):输出到文件，图片文件格式

to\_array\(\)//转化为numpy array

to\_image\(\)//转化为图片对象

例子：

```py
import matplotlib.pyplot as plt
from wordcloud import WordCloud
text=open(r"C:\Users\liuzhan\Desktop\数据及相关的资料\pachong.txt",encoding='utf-8')
mylist=list(text)
word_list=[" ".join(jieba.cut(sentence)) for sentence in mylist]#将分词使用空格连接然后形成列表
new_text=' '.join(word_list)#将列表中的逗号编程空格，此时new_text变成空格连接的词列表
wordcloud=WordCloud(font_path='simhei.ttf').generate(new_text)
plt.imshow(wordcloud)
plt.axis('off')
wordcloud.to_file('wordcloud.png')
```



