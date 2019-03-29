# 1.EffectScatter\(带有涟漪特效动画的散点图\)

> #### 利用动画特效可以将某些想要突出的数据进行视觉突出。

EffectScatter.add\(\) 方法签名

```
add(name, x_axis, y_axis,
    symbol_size=10, **kwargs)
```

* name -&gt; str  图例名称

* x\_axis -&gt; list  x 坐标轴数据

* y\_axis -&gt; list  y 坐标轴数据

* symbol\_size -&gt; int  标记图形大小，默认为 10
* effect\_scale=2.5&gt;&gt;动画中波纹的最大缩放比例。默认为 2.5
* effect\_period=4&gt;&gt;动画持续的时间。默认为 4（s）
* symbol -&gt; str  标记图形，有'rect', 'roundRect', 'triangle', 'diamond', 'pin', 'arrow'可选
* effect\_brushtype -&gt; str   波纹绘制方式，有'stroke', 'fill'可选。默认为'stroke'



