### Cufflinks库的使用方法：

> ### 注意：目前cufflinks只支持jupyter notbook



```
import cufflinks as cf
cf.set_config_file(offline=True,theme='ggplot')
df=cf.datagen.scatter()#返回的df为DataFrame数据结构
df.iplot
#详见：d:\anaconda3\lib\site-packages\cufflinks\plotlytools.py
```

### df.iplot\(\)函数主要参数：

**各参数主要根据kind的不同也改变，基本上是plotly中kind对象中的参数。**

* kind：图形类型&gt;&gt;&gt;scatter
  				bar
  				box
  				spread
  				ratio
  				heatmap
  				surface
  				histogram
  				bubble
  				bubble3d
  				scatter3d	
  				scattergeo
  				ohlc
  				candle
  				pie
  				choroplet
* x：x轴数据
* y:y轴数据&gt;&gt;&gt;使用时只需传入df的列名即可
* xTitle：x轴标签
* yTitle：y轴标签
* zTitle：z轴标签
* dash：线的类型
* witdh：宽度
* 




