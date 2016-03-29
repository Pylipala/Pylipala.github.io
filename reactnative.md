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
