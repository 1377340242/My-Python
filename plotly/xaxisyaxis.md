* showline:bool,是否显示轴线
* showgrid：bool，是否显示网格
* showtickelabels：bool，是否显示刻度标签
* linecolor：轴线颜色
* linewitdh：轴线宽度
* ticks：轴线的刻度时在图内还是图外,'outside'/'inside'
* tickwidth:刻度宽度
* tickcolor：刻度颜色
* ticklen：刻度长苏
* tickfont：刻度的字体样式，大小，颜色&gt;tickfont=dict{family:’Arial‘,size=12,color='black'}
* zeroline:bool,是否显示零线
* zerocolor：零线颜色
* zerowitdh：零线宽度
* type：轴的类型，"-" \| "linear" \| "log" \| "date" \| "category" \| "multicategory" 默认’-‘
* side：坐标轴的位置， "top" \| "bottom" \| "left" \| "right"
* domain：轴的坐标区域\[0,1\]。
* title：轴的标签
* overlaying：覆盖的意思，overlaying=’free‘、’x‘、’y‘，覆盖相应标号的轴
* anchor：与某个轴绑定。anchor=’free‘、\| "/^x\(\[2-9\]\|\[1-9\]\[0-9\]+\)?$/" \| "/^y\(\[2-9\]\|\[1-9\]\[0-9\]+\)?$/"
* titlefont:轴标签的字体
* tickangle=-45:设置刻度标签得旋转角度
* ticksuffix='%':刻度值后缀。
* tickprefix：刻度值前缀
* range=\[0,1\],刻度范围
* dtick=20，坐标间隔px
* rangeslider：滑块，rangeslider=dict{bgcolor='red',bodercolor='red',borderwidth=1,range=list\(\)}
* rangeselector:选择器，rangeselector=dict{button=list\(dict\(step='month'\),stepmode='backward',count=1,label='1m'\)}

step："month" \| "year" \| "day" \| "hour" \| "minute" \| "second" \| "all"

count=1,step=month:表示这个选择器覆盖时间为1xmonth。

