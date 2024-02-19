---
title: "如何保存adb授权"
datePublished: Thu Feb 15 2024 16:00:00 GMT+0000 (Coordinated Universal Time)
cuid: clssmgrco000l08jk0oka55lh
slug: adb
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1708328006811/339b6457-ab6a-4ad6-b48b-0fc75bb98466.jpeg
tags: android, rboy

---

一直不理解那种群控机箱是如何解决ADB授权问题的，才知道安卓的ADB也会自动生成私钥与公钥。

我们的PC机（以windows为例）上启动了adb.exe进程时，adb会在本地生成一对密钥 adbkey(私钥)[与adbkey.pub](http://与adbkey.pub)(公钥);

当你首次启动adb.exe时，会在C盘的当前用户的目录下生成一个".android"目录，[其中adbkey与adbkey.pub](http://其中adbkey与adbkey.pub)就在这个目录下。

adb.exe会在启动时读取这两个文件(没有就重新生成)，所以如果你要是删除或者修改了这两个文件之后，必须要关闭adb.exe进程，重启之后才能生效。

其次Android上，PC的公钥被保存在一个文件中"/data/misc/adb/adb\_keys"

转自 [我想去掉adb授权提示，但我实在搞不懂资料](https://www.uotan.cn/threads/adb.2889/)