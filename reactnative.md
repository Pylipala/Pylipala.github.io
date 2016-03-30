React实践笔记
=====
#程序入口
文档不会跟你讲的是
```
AppRegistry.registerComponent('client333', () => client);
```
这里的第一个参数`client333`要和
```
  RCTRootView *rootView = [[RCTRootView alloc] initWithBundleURL:jsCodeLocation
                                                      moduleName:@"client333"
                                               initialProperties:nil
                                                   launchOptions:launchOptions];
```
的`moduleName`参数匹配。

#本地文档
因为访问github.io上面的文档总是不够快，所以想下载一份本地拷贝，方便查看。
# clone react-native
# 切换到gh-page分支
# 在react-native父目录启动服务器 `python -m SimpleHTTPServer`
# 通过浏览器访问`http://localhost:8000/react-native/`就可以看到漂亮的文档啦
注意，父目录的其他文件也会被服务出来，有安全隐患哦。
