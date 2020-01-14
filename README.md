# 源码路径  
https://github.com/KuangAlbert/IntelligentMonitoring

# 界面展示  
 软件图标：  
  ![img]( https://raw.githubusercontent.com/KuangAlbert/IntelligentMonitoring/master/favicon.ico)  
 炫酷黑主题：  
   ![img](https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/%E7%82%AB%E9%85%B7%E9%BB%91%E4%B8%BB%E9%A2%98.jpg)  
星空灰主题：  
![img]( https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/%E6%98%9F%E7%A9%BA%E7%81%B0%E4%B8%BB%E9%A2%98.jpg)

# 考勤助手使用说明
打包好的exe路径如下：  
下载最新版本文件夹下的Monitoring.7z，解压后运行Monitoring.exe即可
 ![img](https://github.com/KuangAlbert/IntelligentMonitoring-reased/blob/master/img/Snipaste_2020-01-10_10-52-53.jpg)
 ![img](https://github.com/KuangAlbert/IntelligentMonitoring-reased/blob/master/img/Snipaste_2020-01-10_10-54-54.jpg)

## 运行环境确认
1. 电脑需要安装Chrome浏览器
2. 谷歌浏览器的版本要与Chromerdirver.exe的版本匹配，我的git仓库的Chromerdirver.exe的版本是79.0.3945.36，如果需要更换，请点击下面的链接下载相匹配的exe替换掉跟Monitoring.exe在同一目录的Chromerdriver.exe即:  
http://npm.taobao.org/mirrors/chromedriver/  
http://chromedriver.storage.googleapis.com/index.html  
 ![img](https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/Snipaste_2020-01-08_18-43-31.jpg)
3. 查看谷歌浏览器版本的方法是  
![img](https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/Snipaste_2020-01-08_18-44-52.jpg)  
![img](https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/Snipaste_2020-01-08_18-45-03.jpg) 
4. Monitoring.exe必须和Chromedriver.exe在同一目录，否则需要把Chromedriver.exe目录添加到Windows的环境变量中  

# 功能说明
1、实时爬取最近三天（昨天、前天、大前天）的考勤数据，包括上班时间、下班时间、加班时间；  
2、显示今天的早上打卡时间  
3、根据早上的打卡时间，实时计算今天已经加班的时间数  
4、根据早上的考勤的时间和当前时间，计算黄金下班时间（公司的考勤是按15分钟计算的，没满15分钟都会被舍去）  
5、显示半月的加班总时数  
6、填写加班申请，支持填写最近三天的加班（默认填写昨天）
- 智能填写：智能填写加班日期、加班时间段、加班小时数
- 直接填写：只填写加班日期，适合考勤没刷新的情况  
 ![img](https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/%E5%8A%A0%E7%8F%AD%E7%94%B3%E8%AF%B7%E5%9B%BE.png)
 ![img]( https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/Snipaste_2020-01-08_16-57-56.jpg)

7、手动计算黄金下班时间：用于考勤没刷新的时候，预估出最佳的下班时间  
8、默认是15分钟刷新一次数据，刷新时间设置  
9、支持手动刷新  
10、默认会根据当前日期判断今天是周末还是工作日，但不排除有时补班和节假日的情况，因此有手动按钮应付这种特殊情况

# 背景介绍
针对某公司的加班制度用python编写的一个小工具  
1. 公司实现弹性下班制度，7:30-9:30上班可卡都可以，如果在7:30之前打卡则按7:30计算
2. 中午的午休时间（12:30-13:15）不计算在工作时间内，共0.75h
3. 加班半个小时才算加班
4. 考勤时间按15分钟为单位计算，不满15分钟的都舍去  
 ![img]( https://github.com/KuangAlbert/IntelligentMonitoring/blob/master/ReadmeImage/Snipaste_2020-01-08_18-35-38.jpg)

# python运行依赖的库
如需自己运行修改，需要安装以下python库
- pyinstaller
- lxml
- pyqt5
- pyqt5-tools
- selenium
- pandas
- qdarkstyle

IDE开发环境：Pycharm201902  
Python版本:3.8.1

# 更新历史和作者信息
作者：狂暴风雷  

发布日期 | 版本 | 发布说明
---|---|---
20200108 | V1.0 | 实现了基本功能和界面
20200110 | V2.0 | 1、修复了一些bug<br>2、增加了消息提示输出<br>3、设置窗口为固定大小
20200111 | V3.0 | 1、实现自动更新开关、自动更新频率、皮肤设置的保存<br>2、增加“查看更新“按钮，按钮直接链接到本版本库，方便用户获取最新版本<br>3、调整控件位置，使更符合审美<br>4、增加主题设置，内置星空灰、炫酷黑两款主题，可以自由切换<br>5、”自动更新频率“窗口只能输入2-9999的整形数<br>6、实现无边框，使窗口看起来更炫酷<br>7、本软件由”打工助手“改为”考勤助手“<br>8、增加软件图标，包括任务栏图标


# 已知问题
1. 当没有爬取结束时，关闭打工助手会导致后台有残留ChromeDirver进程，预计下一版本通过增加关闭按钮，来回调一个函数关闭打开的ChromeDriver进程
2. 用pyinstaller打包层单个exe文件后，启动非常慢，暂时没有解决办法
3. 在一些win10 64位有打开窗口变小的bug，原因未知
  
