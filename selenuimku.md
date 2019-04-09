#### selenuim中文文档：[https://python-selenium-zh.readthedocs.io/zh\_CN/latest/](https://python-selenium-zh.readthedocs.io/zh_CN/latest/)

> ## 经验总结：

##### 1.获取网页HTML内容

```
#导入必要的库
from selenium import webdriver
from bs4 import BeautifulSoup
import time
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
```

```
driver = webdriver.Chrome(executable_path="D:\Software\chromedriver\chromedriver.exe")#创建一个driver，用于控制浏览器
driver.get(url)#打开url
source=driver.page_source#得到网页界面资源（与源代码不同）包含所有界面信息（包括AJAX数据）
```

##### 2.使用BeautifulSoup解析source，提取想要的数据

##### 3.如果需要再次打开网页........

```
driver.execute_script("window.open('%s')"%url)#打开另一个窗口
handles=driver.window_handles#f返回所有窗口
current_handle=driver.current_window_handle#当前控制窗口
driver.switch_to.window(driver.window_handles[1])#将控制窗口转移到另外窗口
```

### 常用命令：

driver.close\(\)\#关闭当前窗口

driver.quit\(\)\#关闭所有窗口，即关闭浏览器

back\(\)  
，forward\(\) 浏览器的后退和前进

##### 

cookie操作

\`get\_cookies\(\)

# 返回所有cookie\`

\`delete\_all\_cookes\(\)

# 删除所有cookie\`

`add_cookie()#添加cookie`

显示等待。。。。

```
wait=WebDriverWait(self.driver,5).until(EC.presence_of_element_located((By.CLASS_NAME,'pager_next')))
常用的判断条件：
title_is 标题是某内容
title_contains 标题包含某内容
presence_of_element_located 元素加载出，传入定位元组，如(By.ID, 'p')
visibility_of_element_located 元素可见，传入定位元组
visibility_of 可见，传入元素对象
presence_of_all_elements_located 所有元素加载出
text_to_be_present_in_element 某个元素文本包含某文字
text_to_be_present_in_element_value 某个元素值包含某文字
frame_to_be_available_and_switch_to_it frame加载并切换
invisibility_of_element_located 元素不可见
element_to_be_clickable 元素可点击
staleness_of 判断一个元素是否仍在DOM，可判断页面是否已经刷新
element_to_be_selected 元素可选择，传元素对象
element_located_to_be_selected 元素可选择，传入定位元组
element_selection_state_to_be 传入元素对象以及状态，相等返回True，否则返回False
element_located_selection_state_to_be 传入定位元组以及状态，相等返回True，否则返回False
alert_is_present 是否出现Alert
```

##### 查找元素的常用方法：

\#\#\#\#\#查找单个元素

find\_element\_by\_name

find\_element\_by\_id

find\_element\_by\_xpath

find\_element\_by\_link\_text

find\_element\_by\_partial\_link\_text

find\_element\_by\_tag\_name

find\_element\_by\_class\_name

find\_element\_by\_css\_selector

\#\#\#\#\#查找多个元素

find\_elements\_by\_name

find\_elements\_by\_id

find\_elements\_by\_xpath

find\_elements\_by\_link\_text

find\_elements\_by\_partial\_link\_text

find\_elements\_by\_tag\_name

find\_elements\_by\_class\_name

find\_elements\_by\_css\_selector

元素操作：

elements.text\#返回元素文本

elements.get\_attribute\('属性名'\)\#返回属性

