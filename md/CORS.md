# CORS

1. 安装扩展(解决跨域)

[佛跳墙VPN(永久免费)](https://www.haoxixin.com/cn/?a=tm#zero)

[Allow CORS: Access-Control-Allow-origin](https://mybrowseraddon.com/access-control-allow-origin.html)

使用正确的上网方式搜索安装扩展，点击`toggle on`开启扩展，可以右键->选项中设置白名单等。

2. 关闭安全策略(解决跨域)

通过命令行启动chrome：
```
open -a "Google Chrome" --args --disable-web-security  --user-data-dir
```
设置参数`--args --disable-web-security`关闭同源策略
`chrome 48` 命令行启动不支持设置跨域了,想要跨域,还需要需要在加上 `—user-data-dir`

* windows
```
"C:\Users\UserName\AppData\Local\Google\Chrome\Application\chrome.exe" --disable-web-security --user-data-dir
```
不知道`chrome.exe` 地址的话，右键chrome图标-->属性-->如下图-->图中 目标 就是文件的位置了，直接复制出来即可

* mac
```
//chrome 浏览器
open -a "Google Chrome" --args --disable-web-security  --user-data-dir
//safari 浏览器 
open -a '/Applications/Safari.app' --args --disable-web-security --user-data-dir 
```

* linux
```
chromium-browser --disable-web-security
```

2.1 自定义启动脚本

* 创建文件夹
```
mkdir myChromeDevUserData
```
* 进入文件夹
```
cd myChromeDevUserData
```
* 查看文件夹目录
```
pwd
结果：/Users/yunxi/Desktop/myChromeDevUserData
```
* 编写脚本(.command或.app)
```
#!/bin/sh
open -n -a '/Applications/Google Chrome.app' --args --user-data-dir="/Users/yunxi/Desktop/myChromeDevUserData" --disable-web-security
```
* 设置权限
```
chmod +x  Chrome.command
```
* 启动
直接双击 Chrome.command 会闪出一个控制台，然后自动消失。如果不想闪控制台的话，将文件的后缀名 .command 改为 .app ，以后直接双击就可以了。