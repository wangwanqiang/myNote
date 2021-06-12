# chromium

## chromium 代理完美解决办法

### git的代理设置

git config --global http.proxy 127.0.0.1:10809

git config --global https.proxy 127.0.0.1:10809

### winhttp的代理设置

netsh winhttp set proxy 127.0.0.1:10809（控制台运行时需要以管理员权限打开）

### cipd\_client的代理设置

cipd\_client项目来源于 [https://github.com/luci/luci-go/tree/master/cipd/client/cipd](https://github.com/luci/luci-go/tree/master/cipd/client/cipd) 通过源码分析使用的是golong的net/http库访问http/https，可通过环境变量设置代理

set HTTP\_PROXY=127.0.0.1:1081 （注意不要加[http://或者https://）](http://或者https://）) 

set HTTPS\_PROXY=127.0.0.1:10809（注意不要加[http://或者https://）](http://或者https://）)

本地代理\(VPN\)要求1081端口是本地http/https代理服务， 如果是socks5代理cipd\_client是不支持的， 需要使用privoxy.exe再做一层http/https代理 

 原文链接：[https://blog.csdn.net/tdgx2004/article/details/66965675](https://blog.csdn.net/tdgx2004/article/details/66965675)

