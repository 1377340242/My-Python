# 柱状图

## 1.Bar

```text
add(name='图例名称',x_axis=x轴数据,y_axis=y_轴数据，is_stack=True/False,bar_category_gap="20%柱的间隔",**args)
```

主要参数\*\*args:

* name:str&gt;&gt;&gt;图例名称
* x\_\_axis:li\_st\(str\)&gt;&gt;x轴数据，可进行拼接  x\_axis=x\*2
* y\_axis:list&gt;&gt;y轴数据,也可进行数据拼接   _y_\_axis=y1+y2
* is\_stack=:bool&gt;&gt;是否堆叠
* bar\__categort\_gap:str&gt;&gt;_柱的间距
* is\_convert :bool&gt;&gt;是否交换 XY 轴
* is\_label\_show:bool&gt;&gt;是否在柱上方显示数据
* is\_datazoom\_show:bool&gt;&gt;是否使用滑块
* datazoom\_type="inside"&gt;&gt;鼠标拖动浏览数据
* datazoom\_range=\[10, 25\]&gt;&gt;滑动范围
* label\_pos='inside'&gt;&gt;设置数值的显示位置
* label\_color=\['rgba\(0,0,0,0\)'\]&gt;&gt;设置柱状的颜色
* xaxis\_interval=0&gt;&gt;x轴显示间隔
* yaxis\_interval=0&gt;&gt;y轴显示间隔
* xaxis\_rotate=30, yaxis\_rotate=30&gt;&gt;设置刻度数值的角度
* mark\_line=\["average"\]&gt;&gt;标记线
* mark\_point=\["max", "min"\]&gt;&gt;标记点
* xaxis\_line\_color="green"&gt;&gt;x轴线的颜色
* xaxis\_line\_width=5&gt;&gt;x轴线的宽度
* xaxis\_label\_textcolor="black"&gt;&gt;x轴标签文本的颜色

```text
#导入Bar类
from pyecharts import Bar

#x_axis,y_axis数据
attr = ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
v1 = [5, 20, 36, 10, 75, 90]
v2 = [10, 25, 8, 60, 20, 80]
#实例化Bar,>>Bar(title="猪标题", subtitle="子标题")
bar = Bar("柱状图数据堆叠示例")

#使用add()函数添加柱状>>>
bar.add("商家A", attr, v1, is_stack=True)
bar.add("商家B", attr, v2, is_stack=True)
```

## 2.Bar3D\(3D柱状图\)

```text
add(name, x_axis, y_axis, data,
    grid3d_opacity=1,
    grid3d_shading='color', **kwargs)
```

* name -&gt; str 图例名称
* x\_axis -&gt; str x 坐标轴数据。需为类目轴，也就是不能是数值。
* y\_axis -&gt; str y 坐标轴数据。需为类目轴，也就是不能是数值。
* data -&gt; \[list\], 包含列表的列表 数据项，数据中，每一行是一个『数据项』，每一列属于一个『维度』
* grid3d\_opacity -&gt; int  
  3D 笛卡尔坐标系组的透明度（柱状的透明度），默认为 1，完全不透明。

  ```text
                 grid3d\_shading -&gt; str
  ```

  三维柱状图中三维图形的着色效果。

  ```text
                  color：只显示颜色，不受光照等其它因素的影响。

                  lambert：通过经典的 lambert 着色表现光照带来的明暗。

                 realistic：真实感渲染，配合 light.ambientCubemap 和 postEffect 使用可以让展示的画面效果和质感有质的提升。ECharts GL 中使用了基于物理的渲染（PBR\) 来表现真实感材质。
  ```

* is\_grid3d\_rotate：bool&gt;&gt;启动自动旋转功能
* grid3d\_rotate\_speed =180&gt;&gt;调节旋转速度

