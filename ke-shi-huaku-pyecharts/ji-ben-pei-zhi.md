# 快速开始：

> * ### add\(\) 主要方法，用于添加图表的数据和设置各种配置项
> * ### print\_echarts\_options\(\) 打印输出图表的所有配置项
> * ### render\(\) 默认将会在根目录下生成一个 render.html 的文件，支持 path 参数，设置文件保存位置，如 render\(r"e:\my\_first\_chart.html"\)，文件用浏览器打开。
> * ### 如果想要提供更多实用工具按钮，请在 add\(\) 中设置 is\_more\_utils 为 True

# 使用主题：

> \#bar.use\_theme\('dark'\) 使用‘dark’主题

# 图像绘制过程：

#### ![](/assets/QQ图片20190329232704.png)多次显示图标

> ### from pyecharts.engine import create\_default\_environment
>
> #### env = create\_default\_environment\("html"\)
>
> #### \# 为渲染创建一个默认配置环境
>
> #### \# create\_default\_environment\(filet\_ype\)
>
> #### \# file\_type: 'html', 'svg', 'png', 'jpeg', 'gif' or 'pdf'
>
> #### env.render\_chart\_to\_file\(bar, path='bar.html'\)
>
> #### env.render\_chart\_to\_file\(line, path='line.html'\)

# 图标配置：

## 1.图形初始化

> 图表类初始化所接受的参数（所有类型的图表都一样）。

* title -&gt; str  
      默认 -&gt; ""  
       主标题文本，支持 \n 换行。

* subtitle -&gt; str  
      默认 -&gt; ""  
    副标题文本，支持 \n 换行。

* width -&gt; int  
    默认 -&gt; 800（px）

  画布宽度。

* height -&gt; int  
   默认 -&gt; 400（px）

  画布高度。

* title\_pos -&gt; str/int  
     默认 -&gt; 'left'  
   标题距离左侧距离，有'auto', 'left', 'right', 'center'可选，也可为百分比或整

* title\_top -&gt; str/int  
  默认 -&gt; 'top'  
    标题距离顶部距离，有'top', 'middle', 'bottom'可选，也可为百分比或整数

* title\_color -&gt; str   默认 -&gt; '\#000'  
    主标题文本颜色。

* subtitle\_color -&gt; str  
     默认 -&gt; '\#aaa'  
   副标题文本颜色

* title\_text\_size -&gt; int  
     默认 -&gt; 18  
     主标题文本字体大小。

* subtitle\_text\_size -&gt; int
     默认 -&gt; 12
    副标题文本字体大小。
* background\_color -&gt; str
     默认 -&gt; '\#fff'
    画布背景颜色
* page\_title -&gt; str
    默认 -&gt; 'Echarts'
    指定生成的 html 文件中 &lt;title&gt; 标签的值。
* renderer -&gt; str
    默认 -&gt; 'canvas'
    指定使用渲染方式，有 'svg' 和 'canvas' 可选。3D 图仅能使用 'canvas'。
* extra\_html\_text\_label -&gt; list
  额外的 HTML 文本标签，\(&lt;p&gt; 标签\)。类型为 list，list\[0\] 为文本内容，list\[1\] 为字体风格样式（选填）。如 \["this is a p label", "color:red"\]。仅限于在单个图形或者 page 类时使用。
* is\_animation -&gt; bool
     默认 -&gt; True
    是否开启动画

## 2**.通用配置**

## 通用**配置项**

* xyAxis：平面直角坐标系中的 x、y 轴。\(Line、Bar、Scatter、EffectScatter、Kline\)

* dataZoom：dataZoom 组件 用于区域缩放，从而能自由关注细节的数据信息，或者概览数据整体，或者去除离群点的影响。\(Line、Bar、Scatter、EffectScatter、Kline、Boxplot\)

* legend：图例组件。图例组件展现了不同系列的标记\(symbol\)，颜色和名字。可以通过点击图例控制哪些系列不显示。

* label：图形上的文本标签，可用于说明图形的一些数据信息，比如值，名称等。

* lineStyle：带线图形的线的风格选项\(Line、Polar、Radar、Graph、Parallel\)

* grid3D：3D笛卡尔坐标系组配置项，适用于 3D 图形。（Bar3D, Line3D, Scatter3D, Surface3D\)

* axis3D：3D 笛卡尔坐标系 X，Y，Z 轴配置项，适用于 3D 图形。（Bar3D, Line3D, Scatter3D, Surface3D\)

* visualMap：是视觉映射组件，用于进行『视觉编码』，也就是将数据映射到视觉元素（视觉通道）

* markLine-markPoint：图形标记组件，用于标记指定的特殊数据，有标记线和标记点两种。（Bar、Line、Kline）

* tooltip：提示框组件，用于移动或点击鼠标时弹出数据内容

* toolbox：右侧实用工具箱

上述具体参数见：

官网---------&gt;[http://pyecharts.org/\#/zh-cn/charts\_configure?id=%E9%80%9A%E7%94%A8%E9%85%8D%E7%BD%AE%E9%A1%B9](http://pyecharts.org/#/zh-cn/charts_configure?id=%E9%80%9A%E7%94%A8%E9%85%8D%E7%BD%AE%E9%A1%B9)



