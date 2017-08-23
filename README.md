# RSBugtagsDemo
OC 集成 Bugtags bug 反馈工具的 Demo

![](https://img.shields.io/badge/platform-iOS-red.svg) 
![](https://img.shields.io/badge/language-Objective--C-orange.svg) 
![](https://img.shields.io/badge/download-55.7MB-brightgreen.svg)
![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg) 

Bugtags是国内首款为改善移动产品质量而专门打造的测试平台产品。使用Bugtags平台可以随时随地对移动产品提出准确的改善意见，使得测试更简单，修复问题更轻松，产品用户满意度更高。

产品综述Bugtags采用独创的所见即所得的问题上报方式，有效提高了问题上报的效率和问题描述的准确度；同时平台提供了自动收集分析崩溃信息与问题生命周期管理功能。使用Bugtags平台，能够帮助移动开发团队快速定位和解决问题，最终有效提升产品质量。

| 名称 |1.列表页 |2.反馈操作页 |3.反馈页 |
| ------------- | ------------- | ------------- | ------------- |
| 截图 | ![](http://og1yl0w9z.bkt.clouddn.com/17-8-23/74353286.jpg) | ![](http://og1yl0w9z.bkt.clouddn.com/17-8-23/39222276.jpg) | ![](http://og1yl0w9z.bkt.clouddn.com/17-8-23/31465183.jpg) |
| 描述 | 通过 storyboard 搭建基本框架 | 反馈 Bug 操作展示 | 可视化提交 Bug 样式 |


## Advantage 优势
* 极速集成
　一行代码，开启高效测试
* 所见即所得提交
　在你的应用中直接提交 Bug，方便快捷
* 自动记录运行时数据
　界面截图、设备信息、控制台日志、操作步骤，一项也不少
* 全民参与测试
  测试零门槛，产品经理、设计师、客服都能快速参与

## Installation 安装
### 1.手动安装:
1.下载 SDK 压缩包并解压缩(http://bugtags.com/url/ios)

将 Bugtags.framework 和 Bugtags.bundle 文件夹拖到 Xcode 项目中

2.在应用的设置中，Build Phases -> Link Binary With Libraries 里添加以下 frameworks 及 libraries：

```
UIKit            AVFoundation      Foundation        SystemConfiguration
QuartzCore        CoreLocation      ImageIO            Security       CFNetwork     libc++.tbd
```

3.重要！ 在应用对应 target 的设置中，Build Settings -> Linking 项下的 Other Linker Flags 中添加 -ObjC（如果已有，则不需要再添加）注意 O,C 大写 

![](http://og1yl0w9z.bkt.clouddn.com/17-8-23/62776766.jpg)

### 2.CocoaPods安装:

修改“Podfile”文件

```
pod 'Bugtags'
```

控制台执行 Pods 安装命令 

```
pod install
```

> 如果 pod search 发现不是最新版本，在终端执行pod setup命令更新本地spec镜像缓存，重新搜索就OK了

## Requirements 要求
* iOS 7+
* Xcode 8+


## Usage 使用方法
### 第一步 在 AppDelegate.m 中引入头文件
```
#import <Bugtags/Bugtags.h>
```
### 第二步 简单调用
Objective-C

```
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
//BugtagsOptions *options = [[BugtagsOptions alloc] init];
//options.trackingUserSteps = YES; // 具体可设置的属性请查看 Bugtags.h
    [Bugtags startWithAppKey:@"APP_KEY" invocationEvent:BTGInvocationEventBubble];
    return YES;
}
```

Swift 3

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
//let options = BugtagsOptions()
//options.trackingUserSteps = true // 具体可设置的属性请查看 Bugtags.h
    Bugtags.start(withAppKey: "APP_KEY", invocationEvent: BTGInvocationEventBubble)
    return true
}
```

使用简单、效率高效、进程安全~~~如果你有更好的建议,希望不吝赐教!


## License 许可证
RSBugtagsDemo 使用 MIT 许可证，详情见 LICENSE 文件。


## Contact 联系方式:
* WeChat : WhatsXie
* Email : ReverseScale@iCloud.com
* Blog : https://reversescale.github.io

