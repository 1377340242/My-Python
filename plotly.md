# plotly使用：

```
import plotly as py
py.offline.init_notebook_mode()
import plotly.graph_objs as go
pyplot=py.offline.iplot
```

创建流程：

* 创建图轨数据，使用scatter等命令,
* 设置画面布局，layout
* 集成图形、布局数据，命令有Data\(已被丢弃，使用\[trace0,trace1\]\)，Figure
* 绘制图形输出，iplot或plot



