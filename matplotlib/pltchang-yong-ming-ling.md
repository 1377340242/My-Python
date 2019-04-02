* plt.plot\(\):构建折线图

> 主要参数：
>
> x轴数据
>
> y轴数据
>
> fmt:str格式化字符串
>
> linewidth:线宽
>
> color:线的颜色
>
> alpha:透明度
>
> label：图例名称
>
> marker：标记
>
> t = np.arange\(0., 5., 0.2\)
>
> \# red dashes, blue squares and green triangles
>
> plt.plot\(t, t, 'r--', t, t\*\*2, 'bs', t, t\*\*3, 'g^'\)&gt;&gt;也可以同时plot多个数据

* plt.ylabel\(str \)  为当前axes添加y轴标签
* plt.xlabel\(str \)  为当前axes添加x轴标签 
* plt.axis\(\)

> 参数：
>
> 无参数时：返回当前轴的范围，\[xmin, xmax, ymin, ymax\]
>
> axis\(\[xmin, xmax, ymin, ymax\]\):设定轴的范围
>
> axis\('off'\)：关闭轴线和轴的标签
>
> axis\('equal'\)：x，y轴的长度一样

* plt.figure\(1, figsize=\(9, 3\)\)

> 参数：
>
> num:画布编号
>
> figsize：元组对象，画布尺寸
>
> dpi：分辨率
>
> facecolor:背景颜色
>
> edgecolor：边框颜色
>
> clear:如果为True，当前figure会被清除
>
> 返回：
>
> figure 对象

* plt.subplot\(\)添加子图，注意会覆盖之前figure下的plt.plot\(\)图形，如果不想覆盖可采用add\_subplot函数。

> 参数：subplot\(\)命令指定numrows, numcols, plot\_number，其中 plot\_number 的范围 从1到numrows\*numcols。如果 numrows \* numcols &lt;10，则subplot命令中的逗号是可选的。因此 subplot\(211\) 与 subplot\(2, 1, 1\) 相同。
>
> 子图\[1,3,1\],代表一行三列中的第一个与plt.subplot\(131\)相同

* plt.subtitle\(str\)     为当前子图添加标题
* plt.clf\(\)删除当前figure
* plt.cla\(\)删除当前axes

\`\`\`

