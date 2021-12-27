---
layout:     post
title:      "Hello 2015"
subtitle:   "Hello World, Hello Blog"
date:       2015-01-29 12:00:00
author:     "Hux"
header-img: "img/post-bg-2015.jpg"
tags:

    - Life
---

Windows 11 对 Android APP 的支持，可能是很多人升级的重要原因。

但如果你还没有升级系统，Windows11 检查工具有从检查安装到设置优化一系列指引。



下载地址： https://aomei.lanzoui.com/s/win11chk



但没有 Root、没有 Magisk 的 Android 是没有灵魂的，甚至于像小蝾一样的基佬搞机爱好者还挺想要 Google Play 的。



有了面具你可以做你想做的事，而手机上嫌麻烦没玩过的朋友，正好可以在这里体验一把，反正成不了砖。

![006dMd5bgy1gfe3bckhwtj306o06omyu.jpg](https://www.dianshouit.com/upload/202111/Ps52-1637044210.jpg)



首先确保你打开了虚拟化、Hyper-V 。

如果之前有安装WSA ，请先卸载。

## 获取整合包   

打开 Github 项目：



```
https://github.com/LSPosed/MagiskOnWSA
```



点击右上角的 Fork （需要登录账号，没有的话自行注册）。



![Fork.png](https://www.dianshouit.com/upload/202111/Ej79-1637044240.png)Fork 完成后到自己的库中，点击 Action 来到任务执行界面，选择 Magisk 。



再点击下方的 Run workflow 执行任务；

这里需要配置参数，默认已填好 magisk, 需要 Google Play 的用户将中间的none 改为 pico (或者 nano、micro…)



点击下方 Run workflow 开始运行。



![pico.png](https://www.dianshouit.com/upload/202111/rC99-1637044329.png)



刷新等待几分钟，任务完成后打开，选择 x64 版本下载（arm用户请下arm64）。



![产物.png](https://www.dianshouit.com/upload/202111/Kt62-1637044356.png)

## 安装    

非官方包是无法直接安装的，所以我们需要先打开任意源安装应用。



可以直接搜索 开发者选项，在开发人员模式 下 激活 从任意源安装应用。



![开发者.png](https://www.dianshouit.com/upload/202111/Q573-1637044426.png)

解压下载好的 zip 文件，找到主目录下的 AppxManifest.xml。

管理员身份运行 PowerShell，执行

```
Add-AppxPackage -Register "你的AppxManifest.xml完整路径"
```

等待部署完成。

## 安装应用   

到这集成 Google Play 和 Magisk 的 WSA 已部署完成，但此时你还是没有能用的应用商店的（Play Store 404）。

一种是使用 WSA Tool ，Microsoft Store 上可以下载，但只能通过链接打开。



```
https://www.microsoft.com/en-us/p/wsatools/9n4p75dxl6fg?activetab=pivot:overviewtab
```

而更推荐的是使用 ADB 命令安装，其实非常简单。



首先都需要打开 WSA 设置，打开开发者选项。



并在其设置中打开无线调试。





返回可以看到 127.0.0.1:58526 的本地 ip 和端口 ；



下载安装 ADB 工具包，双击快捷方式打开命令窗口。





执行 adb 连接命令：



```
adb connect 127.0.0.1:58526
```



检查是否连接成功：



```
adb devices
```





接着安装任何你想要的应用，比如商店、浏览器、文件管理器等基本 APP 。



```
adb install "你要安装的.apk完整路径"
```







同时建议同样的操作安装创建快捷方式，可以方便打开APP、设置。





## 修复Magisk   

打开Magisk 应用，会提示需要安装完整版Magisk ，可以点击下载。



![Magisk 更新.png](https://www.dianshouit.com/upload/202111/D269-1637044665.png)

但网络情况不是太好，且容易闪退，也可以手动安装 apk （需要Magisk debug 版）。





```
https://raw.githubusercontent.com/topjohnwu/magisk-files/canary/app-debug.apk
```



上面有了商店，应该会装浏览器、文件管理器等APP 了吧？

更新 Magisk 后还会提示需要修复运行环境，点击确定，应用将自动重启。



![Magisk 更新3.png](https://www.dianshouit.com/upload/202111/Ze61-1637044683.png)

但有的设备后续还会一直提示这个，取消就行。

现在 Magisk 已可用。



![Snipaste_2021-11-16_10-05-46.png](https://www.dianshouit.com/upload/202111/PK40-1637044715.png)



然后你就可以到模块中安装 LSPosed 框架或者其他模块了。



![Magisk 模块.png](https://www.dianshouit.com/upload/202111/eu63-1637044745.png)

LSPosed 可以到这里下载。





```
https://github.com/LSPosed/LSPosed/releases
```



## 结语    

本文所用到的资源，包括 adb 工具包、Magisk apk（debug-app）、LSPosed 框架除了上面的链接可以官方下载外，也上传了网盘方便大家获取。

可以关注 电手优品，回复 93 获取。

虽然整体操作很简单，但 WSA 的网络可以说是一言难尽，包括 Google Play 也需要我不能说的额外操作（保命啊）。

这点小问题也不是啥问题，毕竟折腾也是种快乐，后续大家自己想怎么玩就怎玩，我就不教了。

 