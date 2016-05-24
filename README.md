## 介绍

JQNetwork，为 Jason Qt Netowrk 的简称

JQNetwork是基于Qt开发，并且未使用除了 C++标准库 和 Qt 之外的第三方库，保证了库的可移植性以及库的纯粹性

所有的传输数据的地方，都使用了TCP长连接，保证了传输数据的可靠性

#### 用到的Qt库有：

* core
* network
* concurrent	
* testlib（测试用，运行不需要）

#### 支持的平台（理论上Qt支持的都可以，下面3个是我测试过的）

* Linux
* Windows
* OS X

推荐使用Linux系统或者Unix系统，因为在5.6后，Qt更换了Unix相关系统的底层模型，从select更换为了poll，这样子网络库的并发就脱离了1024个的限制。

使用本库，需要 Qt5.6.0或者更高版本，以及支持 C++14 的编译器，对操作系统无要求。

本库源码均已开源在了GitHub上。

GitHub地址：https://github.com/188080501/JQNetwork

本库的授权协议是：随便用

方便的话，帮我点个星星，或者反馈一下使用意见，这是对我莫大的帮助。

若你已经有了更好的建议，或者想要一些新功能，可以直接邮件我，我的邮箱是：Jason@JasonServer.com

或者直接在GitHub上提交问题：
https://github.com/188080501/JQNetwork/issues

## 功能介绍

JQNetwork，从TCP开始封装的网络库，目的是为了让Qt开发者更加方便的开发出更加高效、稳定的C/S架构网络程序。

#### 本网络库特性：

* TCP长连接
* 连接复用（对于客户端）
* 连接合并（对于服务器，可前后端分离）
* 全双工
* 全异步
* 多线程（收发、处理分线程）
* 连接代理
* 数据压缩
* SSL支持（会在V1.0版本加入）

## 开发计划

阶段|日期
---|---
功能确定|2016-05
架构确定|2016-06
开始开发|2016-06
V0.1|2016-08
V1.0|2016-10

## 性能介绍

本库性能只能说一般般，底层是poll注定了性能不是强项，以下是我在我电脑（MacBookPro）上，测出的性能。

TCP长连接可以达到 x 个

TCP短连接，每次连接来回发送 128B 数据，每秒可以达到 x 个

本地（127.0.0.1）单个TCP长连接：以单包 128B 来回发送算，每秒可以达 x 包；以单包 32KB 来回发送算，每秒可以达 x 包。

## 模块介绍