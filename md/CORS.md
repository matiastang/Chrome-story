# CORS

1. 安装扩展(解决跨域)

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