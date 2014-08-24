最小的服务器
=======
有时候直接打开本地的html文件，会因为浏览器的安全策略导致无法访问本地文件，特别是Chrome浏览器
```
XMLHttpRequest cannot load file:///Users/liulun/Documents/GitRoot/Pylipala.github.io/config.json. Received an invalid response. Origin 'null' is therefore not allowed access.
```
这时候可以在这个目录下架一个简单地服务器来解决问题。
```
$ python -m SimpleHTTPServer
```
据说Python3里面不一样，是
```
$ python3 -m http.server
```

参考[Stackoverflow](http://stackoverflow.com/questions/3800143/ad-hoc-webserver-for-static-files-on-unix-macosx)

一日不见，如隔三秋
