# B站直播弹幕测试器
一个单html文件版的B站直播弹幕测试工具，使用Vue框架。
## 目的
本项目存在的目的是给另一个项目[danmaqua-android](https://github.com/danmaqua/danmaqua-android) 做预告。我们会把将要实现在`danmaqua-android`中的平台无关的功能预先在这里实现，在接受用户反馈的同时对网页进行快速迭代，待功能的具体细节（如操作逻辑等）确定下之后再在`danmaqua-android`中实现，防止不必要的分包过程。

目前这个项目主要是为了展示和探讨将要实现的“自定义规则的弹幕匹配”功能。
## 部署方法
下载`index.html`，将其当作普通的静态资源部署即可。注意：项目用到了桌面通知(`Notification`)相关API，如果你希望部署在`localhost`之外的服务器上，需要有https，否则桌面通知功能不会激活。

如果你希望自用，那么也可以直接用浏览器打开`index.html`。

## 功能简介

项目提供一个用来测试弹幕匹配规则的环境。

项目提供一些基本的组件：

+ 使用正则表达式匹配弹幕内容
+ 匹配弹幕发送者UID
+ 匹配弹幕发送者昵称
+ 匹配弹幕类型（滚动弹幕、置顶弹幕等等）
+ “并且”逻辑运算
+ “或者”逻辑运算

你可以通过任意数量的上述组件的组合来指定你想要的规则。在指定规则后，你也可以

+ 为规则命名
+ 指定匹配后的行为（以某种样式高亮显示匹配的弹幕，或是屏蔽之）
+ 导入或导出你制定的规则

一个常见的应用场景是：在一场直播中标记主播的同传弹幕，甚至在联动时用多条规则分别标记不同主播的同传弹幕。

另外为了方便在观看直播的同时查看匹配高亮规则的弹幕，项目提供桌面通知的功能。匹配规则的弹幕的内容将通过桌面通知功能展示。

## 注意事项
+ 项目不提供直播画面的观看渠道。如果希望在测试弹幕的同时观看直播，请新开一个浏览器窗口或在手机上观看。
+ 你可以指定任意要连接的直播间，但指定的直播间号须为真实的直播间号而非短房间号。由于跨域规则限制，本项目无法提供短房间号到真实房间号的自动转换。
+ 由于本项目算是一个安卓项目的在线预览版，所以在部分操作逻辑上可能不符合一般的网页，请见谅。
+ 关于桌面通知功能
	+ 如果你使用Windows或OS X操作系统，请授权浏览器发送通知。否则即使在浏览器内授权给网页通知权限，你仍不能收到任何通知提醒。
	+ 如果你使用Linux，且使用须自行配置的窗口管理器（例如i3wm，dwm或awesome），请确保桌面通知守护进程已配置好并正在运行。
	+ 由于火狐浏览器的限制，在打开本网页时不会自动弹出请求桌面通知权限的对话框。这时如果你希望使用项目的桌面通知功能，请点击浏览器地址栏左侧的像信息气泡一样的按钮，手动开启请求授权对话框。
## 使用方法
请跟随网页内提示操作。
## 在线版
在[这里](https://danmaku.meagames.cn)有一个已经部署好的版本，可直接试用。

