> # Pyecharts可视化数据库
>
> 介绍及安装：
>
> 安装：

```
$ pip install pyecharts
```

### \*\*使用 pyecharts-snapshot 插件

\*\*

如果想直接将图片保存为 png, pdf, gif 格式的文件，可以使用 pyecharts-snapshot。使用该插件请确保你的系统上已经安装了`Nodejs`环境。  
[https://nodejs.org/en/download/](https://nodejs.org/en/download/)

安装 phantomjs  首先设置镜像源：$`npm config set registry https://registry.npm.taobao.org`

然后：$`npm install -g phantomjs-prebuilt`

安装 pyecharts-snapshot  $ `pip install pyecharts-snapshot`

调用 render 方法 `bar.render(path='snapshot.png')`文件结尾可以为 svg/jpeg/png/pdf/gif。请注意，svg 文件需要你在初始化 bar 的时候设置 renderer='svg'。

## 中文教程：[http://pyecharts.org/\#/zh-cn/](http://pyecharts.org/#/zh-cn/charts_configure?id=%E9%80%9A%E7%94%A8%E9%85%8D%E7%BD%AE%E9%A1%B9)





