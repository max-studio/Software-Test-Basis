# selenium基础应用

### 准备工作
-安装selenium<br>
首先，下载selenium库<br>
```pip install selenium```<br>

之后导入selenium库，检查是否下载成功。
```
import selenium
```

- 安装浏览器驱动<br>
    Selenium调用浏览器必须有一个webdriver驱动文件。
    1. Chrome驱动文件下载：[chromedriver](https://chromedriver.storage.googleapis.com/index.html?path=2.35/)
    2. Firefox驱动文件下载：[geckodriver](https://github.com/mozilla/geckodriver/releases)
    
   Chrome版本与chromedriver版本对照及下载：
   

chromedirve版本|chrome版本
----|----
ChromeDriver v2.46 (2019-02-01) | Chrome v71-73
ChromeDriver v2.45 (2018-12-10) | Chrome v70-72
ChromeDriver v2.44 (2018-11-19) | Chrome v69-71
ChromeDriver v2.43 (2018-10-16) | Chrome v69-71
ChromeDriver v2.42 (2018-09-13) | Chrome v68-70
ChromeDriver v2.41 (2018-07-27) | Chrome v67-69
ChromeDriver v2.40 (2018-06-07) | Chrome v66-68
ChromeDriver v2.39 (2018-05-30) | Chrome v66-68
ChromeDriver v2.38 (2018-04-17) | Chrome v65-67
ChromeDriver v2.37 (2018-03-16) | Chrome v64-66
ChromeDriver v2.36 (2018-03-02) | Chrome v63-65
ChromeDriver v2.35 (2018-01-10) | Chrome v62-64

 > 下载的浏览器驱动请放在python安装目录下。如果放在其他目录下，请自行配环境。

### selenium的定位方式

- selenium提供了8钟定位方式
    - id
    - name
    - class name
    - tag name
    - link text
    - partial link text
    - xpath
    - css selector
- 8种定位的python方法

    定位一个元素 | 定位多个元素 | 含义
    ---- | ---- | ----
    find_element_by_id() | find_elements_by_id() | 使用元素id定位
    find_element_by_name() | find_elements_by_name() | 使用元素名字定位
    find_element_by_class_name() | find_elements_by_class_name() | 使用元素类名定位
    find_element_by_tag_name() | find_elements_by_tag_name() | 使用标签定位
    find_element_by_link_text() | find_elements_by_link_text() | 使用完整链接定位
    find_element_by_partial_link_text() | find_elements_by_partial_link_text() | 使用部分链接定位
    find_element_by_xpath() | find_elements_by_xpath() | 使用元素xpath路径定位
    find_element_by_css_selector() | find_elements_by_css_selector() | 使用css选择器定位
    
- 举个栗子

    以百度首页为例子.
    ```
        from selenium import webdriver
        driver = webdriver.Chrome()
        # 以下都是查找搜索框
        driver.find_element_by_id('kw')
        driver.find_element_by_class_name('s_ipt')
        driver.find_element_by_name('wd')
        driver.find_element_by_xpath('//*[@id="kw"]')
        # 以下是查找百度一下按钮
        driver.find_element_by_css_selector('#su')
    ```
    
    
### 控制浏览器的一些方法

   方法 | 含义
   ---- |---
   set_window_size() | 设置浏览器大小
   back() | 浏览器后退
   forward() | 浏览器前进
   refresh() | 刷新当前页
   clear() | 清除文本
   send_keys(value) | 模拟按键输入
   click() | 单击元素
   submit() | 用于提交表单
   get_attribute(name) | 获取元素属性
   is_displayed() | 设置该元素是否用户可见
   size | 返回元素的尺寸
   text | 获取元素的文本

### 鼠标事件
需要导入ActionChains类
```
from selenium.webdriver import ActionChains
```

方法 | 说明 
----| ----
ActionChains(driver) | 构造ActionChains对象
click() | 单击
double_click() | 双击
context_click() | 右击
move_to_element(above) | 执行鼠标悬停操作
drag_and_drop(source，target) | 拖动
drag_and_drop_by_offset(source，x,y) | 拖动到某个坐标后松开
perform() | 执行所有 ActionChains 中存储的行为，可以理解成是对整个操作的提交动作
    
### 键盘事件
    需要导入Keys类
```
from selenium.webdriver.common.keys import Keys
```

方法|说明
---|---
send_keys(Keys.BACK_SPACE)|删除键
send_keys(Keys.SPACE)|空格键
send_keys(Keys.TAB)|制表键
send_keys(Keys.ESCAPE)|回退键
send_keys(Keys.ENTER)|回车键
send_keys(Keys.CONTROL,'a')|全选ctrl+a
send_keys(Keys.CONTROL,'c')|复制ctrl+c
send_keys(Keys.F1)|F1
……|……
send_keys(Keys.F12)|F12


### expected_conditions EC

`判断一个元素是否存在，如判断alert弹窗等`

方法 | 说明 
----| ----
title_is | 判断当前页面的title是否完全等于预期字符串
title_contains | 判断当前页面的title是否包含预期字符串
presence_of_element_located | 元素存不存在这个页面（是否存在于dom树中）
visibility_of_element_located | 判断某个元素是否可见
visibility_of | 判断某个元素是否可见，直接传定位到的element
presence_of_all_elements_located |  判断是否至少有1个元素存在于dom树中
text_to_be_present_in_element | 判断某个元素中的text是否包含了预期的字符串
text_to_be_present_in_element_value  | 判断某个元素中的value属性是否包含了预期的字符串
frame_to_be_available_and_switch_to_it | 判断该frame是否可以switch进去，如果可以的话，返回True并且switch进去，否则返回False
invisibility_of_element_located | 判断某个元素中是否不存在于dom树或不可见
element_to_be_clickable |  判断某个元素中是否可见并且是enable的
staleness_of | 等某个元素从dom树中移除
element_to_be_selected | 判断某个元素是否被选中了,一般用在下拉列表
element_selection_state_to_be | 判断某个元素的选中状态是否符合预期
element_located_selection_state_to_be | 判断某个元素的选中状态是否符合预期，传入定位到的locator
alert_is_present | 判断页面上是否存在alert


###等待
等待分为显式等待和隐式等待<br>
显式等待是等待某个条件成立则继续执行，否则在达到最大等待时间就会抛出异常。
```
WebDriverWait(driver,timeout,poll_frequency=0.5,ignored_exception=None)
```
>driver:浏览器驱动<br>
timeout:最长超时时间，默认为秒
poll_frequency：检测的间隔时间，默认为0.5s
ignored_exception：超时后的异常信息，默认抛出NoSuchElementException异常

WebDriverWait一般和until()或until_not()<br>
```
until(method,message='')
until_not(method,message='')
```
隐式等待会等待页面上所有的元素，当脚本执行到某个元素定位时，如果元素存在，则继续，不存在则以轮询的方式不断的判断元素是否存在，直到超出设定时间，抛出异常。
```
implicitly_wait()
```

###多表单切换
在网页中，有可能会遇见frame/iframe表单嵌套的应用，这时需要通过`switch_to.frame()`方法，将当前定位主体切换到
表单内。使用`switch_to.default_content()`回到外层页面。