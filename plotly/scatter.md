### 散点图Scatter：

常用参数：

* showlegend:bool&gt;是否显示图例，默认为True
* opacity:透明度（0,1）,默认为1
* name：图例名称
* x：x轴数据
* y：y轴数据
* mode：图形格式，lines，markers，markers+lines
* line：线条参数,line=dict\(color=‘block’,width=2,shape='linear'/'spline',smoothing='1.0',

dash='solid'/'dot'/'dash',longdash\)

* fill:填充模式，enumerated : "none" \| "tozeroy" \| "tozerox" \| "tonexty" \| "tonextx" \| "toself" \| "tonext" \) 
* fillcolor:填充颜色
* marker：标记，marker=dict{symbol='o',opacity=1.0,size=6,sizeref=0.2,sizemode=‘area',line=dict{width=2,color='red'},showscale=True} &gt;&gt;&gt;line为标记的外轮廓线

**showscale=True显示颜色条,**sizeref当size为数组时设置的缩放系数，sizemode为缩放形式area（面积）、diameter（直径）

* text：元素相应节点的悬浮文本，在鼠标移动到数据时才显示。
* connectgaps:bool，连接数据缺口


