# selenium基础应用

### 准备工作
-安装selenium<br>
首先，下载selenium库<br>
```pip install selenium```<br>

之后导入selenium库，检查是否下载成功。
```python
import selenium
```

- 安装浏览器驱动<br>
    Selenium调用浏览器必须有一个webdriver驱动文件。
    1. Chrome驱动文件下载：[chromedrive](https://chromedriver.storage.googleapis.com/index.html?path=2.35/)
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

    pass
    
    
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
    
    

