<h1 align='center'>python个人总结</h1>



# ==一. python基础==

## 1.1 字符串相关操作







---



## 1.2 列表相关操作







---



## 1.3 字典相关操作







---



## 1.4 元组相关操作







---



## 1.5 面向对象与面向过程^类^





---



# ==二. 模块==

## 1. 内置模块







## 2. 爬虫相关模块



### 1. 解析数据模块

#### `lxml模块`^etree,xpath^

##### 常用方法

| 方法               | 说明             |      |
| :----------------- | ---------------- | ---- |
| eteree.HTML()      | 格式化为HTML代码 |      |
| xpath()            | 根据xpath查找    |      |
| xpath('string(.)') | 格式化当前节点   |      |
|                    |                  |      |
|                    |                  |      |



---



## 3. GUI相关模块

### PYQT5

#### 基础操作

##### 生成一个实时模块

###### PYQT5主窗口模块

> ```python
> from PyQt5.Qt import *
> import sys
> 
> #  1. 创建一个应用程序对象
> app = QApplication(sys.argv)
> 
> # 2. 控件的操作
> # 2.1 创建控件
> windows = QWidget()
> 
> # 2.2 设置控件
> windows.setWindowTitle("$name$")
> windows.resize(500, 500)
> 
> $END
> 
> 
> 
> 
> # 2.3 展示控件
> windows.show()
> # 3. 应用程序的执行,进入到消息循环
> sys.exit(app.exec())
> ```
>
> 





---



# ==三.爬虫==

## 3.1 请求数据

### 3.1.1 返回结果

| 参数         | 说明       | 示例                                                |
| ------------ | ---------- | --------------------------------------------------- |
| .status_code | 返回状态码 | if response.status_code == 200:<br />    保存到列表 |









----









# ==四. 常见错误解决方法==

## 1. requests相关

1. > 错误类型:
   >
   > `ValueError: check_hostname requires server_hostname`
   >
   > 解决方法:
   >
   > `pip install urllib3==1.25.8`
   >
   > 注释:
   >
   > 发生错误是因为urllib3版本过高导致的,降低urllib3版本可修复此错误



---



## 2. 安装模块时报错

1. > 错误类型:
   >
   > ERROR: Could not find a version that satisfies the requirement requests (from versions: none)
   > ERROR: No matching distribution found for requests
   >
   > 使用镜像源;
   >
   > pip install 模块 -i http://pypi.douban.com/simple --trusted-host pypi.douban.com

### 2.1手动安装

1. https://www.lfd.uci.edu/~gohlke/pythonlibs/
2. 把下载的xml文件改成zip
3. 把压缩出来的文件剪切到`D:\ys\pycharm\项目名\venv\Lib\site-packages`下



---



## 3. 移动项目时报错

1. 把`.idea`里面的文件替换为新建项目里面的`.idea`文件
2. 把`venv`根目录里面的`.cfg`后缀的文件替换为新建项目璃面的文件

---



# ==五. 项目相关代码==



---





# ==六. 临时书写==

