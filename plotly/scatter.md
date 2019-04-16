### 散点图Scatter：

常用参数：

* showlegend:bool&gt;是否显示图例，默认为True
* opacity:透明度（0,1）,默认为1
* name：图例名称
* x：x轴数据
* y：y轴数据
* xaxis,yaxis:设置参考轴，默认:xaxis='x',yaxis='y',如果xaxis='x2'则表示x轴以 \`layout.xaxis2\`为参考轴
* mode：图形格式，lines，markers，markers+lines，markers+lines+text
* line：线条参数,line=dict\(color=‘block’,width=2,shape='linear'/'spline',smoothing='1.0',

dash='solid'/'dot'/'dash',longdash\)

* fill:填充模式，enumerated : "none" \| "tozeroy" \| "tozerox" \| "tonexty" \| "tonextx" \| "toself" \| "tonext" \)

  fill使用技巧：

&gt;"tonexty" （图形方向为V时使用）\| "tonextx"（图形方向为h时使用）,表示在两个trace之间填充。

&gt;"tozeroy" \| "tozerox"，填充到x轴和y轴

&gt; "tonext",在一个封闭曲线包含另个曲线之间填充，"toself" 封闭曲线填充

* fillcolor:填充颜色
* marker：标记，marker=dict{symbol='o',opacity=1.0,size=6,sizeref=0.2,sizemode=‘area',line=dict{width=2,color='red'},showscale=True} &gt;&gt;&gt;line为标记的外轮廓线

**showscale=True显示颜色条,**sizeref当size为数组时设置的缩放系数，sizemode为缩放形式area（面积）、diameter（直径）

* text：list\(str\)元素相应节点的文本，当mode中包含’text‘时文本直接显示，否则，鼠标悬停显示。
* textposition：文本位置，'bottom center'，’top right‘，’bottom right‘，’top center‘
* textfont：文本字体格式
* connectgaps:bool，连接数据缺口



