# appium 基础应用
 > 注意：appium是安卓app测试，请自行将安装环境配置好，这里不再另外说明安卓环境。
### 准备工作
   - 安装appium
     > 建议安装Appium-Desktop版本，Appium-server版本已经停止更新。
        - Appium-Desktop下载：[appium-desktop](https://github.com/appium/appium-desktop/releases)
        ![下载提示](../image/appium-desktop.png)
        - Appium-server下载：[appium-server](https://bitbucket.org/appium/appium.app/downloads/)
        ![下载提示](../image/appium-server.png)
        
   - 安装Appium-Python-Client<br>
       进入cmd,输入一下代码：
       ```pip install Appium-Python-Client```
       >如果遇到遇到下载缓慢的问题，可以将pip的下载源更换为国内的镜像网站，推荐使用清华大学的镜像站。
       更换方法为：在你的c盘下user（用户）文件夹里的用户名（自己取的名字）文件夹下新建一个pip文件，在pip文件夹下新建pip.ini文件并在文件中写入下面的内容：
       \[global]<br>
        index-url = https://pypi.tuna.tsinghua.edu.cn/simple<br>
        即可。
       
      ![图片提示](../image/pip换源.png)
      
### appium基础语法
   - 初始化语句 
       pass    
      