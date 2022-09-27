GitHub地址：https://github.com/kllll1119/MiniWebClient  
B站地址：https://www.bilibili.com/video/BV1aV4y1M7dM  
  
## Why MiniWebClient?  
1、使前端开发桌面程序更加便捷，减少桌面程序的学习成本  
2、修改一个配置前端即可进行桌面程序的逻辑开发，几乎零成本  
3、提供C++端对前端的功能支持，使前端亦可操作计算机底层  

  
## 更新日志
* 2022-09-17 V1.0  
  * 初框架搭建  
* 2022-09-21 V1.1  
  * 性能优化，JS接口新增：隐藏窗口  
* 2022-09-23 V1.2  
  * 工程配置新增标题栏显示  
  * 新增JS接口：隐藏显示标题栏  		   
* 2022-09-23 V1.3  
  * 优化托盘双击恢复主界面  
  * 新增C++加载主界面，调用JS，通知初始化信息	
  * 新增JS接口：用默认浏览器打开网页  
  * 新增404页面功能  
  * 新增弹窗功能  
* 2022-09-24 V1.4  
  * 增加窗口阴影，优化背景，移除404默认值  
  * 增加关于菜单  		   
* 2022-09-24 V1.5  
  * 新增JS接口：显示隐藏当前窗口  
* 2022-09-25 V1.6.1  
  * 增加JS接口：最大化、最小化窗口  
  * 增加再次打开程序或快捷方式，呼出主界面功能  
* 2022-09-27 V1.7.0  
  * 新增JS接口：前进、后退、刷新  
  * 新增JS接口：截图功能  
  				   

## 工程配置
路径：conf/config.ini  
[project]  
;主界面网页地址配置  
;打开本地页面（这个是相对当前工程的路径如：dir/1.html）：404.html  
;打开网页(如果是配置网页必须带http前缀)：https://www.baidu.com  
url_man=demo.html  
  
;404页面配置，目前只支持配置本地文件，所有返回页面错误(网页不返回200)都会打开它，路径为主程序的相对路径，示例：404/404.html  
url_404=  
  
;界面默认宽度  
width = 1360  
;界面默认高度  
height = 900  
  
;显示标题栏，默认值1（1-显示，0-不显示）  
show_title_bar = 1  


## JS调用C++接口
//改变窗体大小  
TFunctionCpp.Excute('set_client_size',{"width":800,"height":600})  
  
//显示/隐藏窗口，0-隐藏，1-显示  
TFunctionCpp.Excute('show_client',{"show":0})  
  
//显示/隐藏标题栏，0-隐藏，1-显示  
TFunctionCpp.Excute('show_title_bar',{"show":0})  
  
//最大化窗口，多次调用为最大化和恢复窗口  
TFunctionCpp.Excute('max_window',{})  
  
//最小化窗口  
TFunctionCpp.Excute('min_window',{})  
  
//退出程序  
TFunctionCpp.Excute('exit_client',{})  
  
//以默认浏览器打开网页  
TFunctionCpp.Excute('open_url',{"url":"http://www.baidu.com"})  

//Web页面：前进  
TFunctionCpp.Excute('go_forward',{})  

//Web页面：后退  
TFunctionCpp.Excute('go_back',{})  

//Web页面：刷新  
TFunctionCpp.Excute('refresh',{})  
  
//网页弹窗,center_window为1的时候窗口居中，此时xpos和ypos不生效，show_title_bar显示/隐藏标题栏：0-隐藏，1-显示  
//注：PopWebWindow只支持一个弹窗，执行多次也是打开一个窗口  
TFunctionCpp.Excute('pop_web_window',{"url":"http://www.baidu.com","width":500,"height":300,"xpos":100,"ypos":100,"center_window":0,"show_title_bar":1}) 

//截图功能，hide_cur_window:截图时是否隐藏当前窗口，0-不隐藏（默认），1-隐藏  
TFunctionCpp.Excute('screen_shot',{"hide_cur_window": 1})  
  
## C++调用JS接口
//打开主界面时，程序默认会调用js方法，用法见demo.html  
TFunctionCallBack("client_info", {"client_version":"1.0.0"}  

其他接口暂未提供，原则上也是TFunctionCallBack调用js，type和msg不同，如有需要C++支持的功能需要定制  

## 如何打开调试控制台
1、交流群下载devtools_resources.pak调试器  
2、将之放到cef目录  
3、重启程序  
4、再次打开程序，按f12即可唤出调试程序了


## 程序运行环境
暂只支持Windows平台(Win7及以上，推荐Win10)

  
## 程序日志路径 
文档\MiniWebClient\log（暂时是主程序在使用）  


## 作者联系方式
QQ：2276386149  
QQ交流群：687085061  

