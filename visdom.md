> # 安装Visdom
>
> pip install visdom
>
> 启动visdom服务器：
>
> cmd：python -m version.server

## visdom.maplot :

参数：

plt：maplotlib.pyplot 中的plt

## visdom.plotlyplot:

参数：

figure：plotly figure对象。

## visdom.image\(\)：

参数：

img：三通到图片数组（H\*W\*C）或者单通道（H\*W）。

win:

env:

opts:dict  用法：opts=dict\(title='标题'，caption='图片标题'\)

```py
from visdom import Visdom
from PIL import Image
import numpy as np
image=Image.open(r"E:\毕业论文\第五章\丝杠\丝杠-1.jpg")
image=np.array(image)
image=image.transponse((2,0,1))#通道转换
vis=Visdom(image,opts=dict(title='标题'，caption='图片标题'))
```

## visdom.images\(\):

参数与visdom.image\(\)相似，只不过要求img为思维数据（B\*H\*W\*C），B代表图片数量

nrow=8&gt;&gt;默认8行

