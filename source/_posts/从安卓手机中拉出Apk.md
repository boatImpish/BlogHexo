---
title: 从安卓手机中拉出Apk
tags: Android
categories: 编程
abbrlink: 6f7bfefe
date: 2022-03-30 22:36:18
---

如何快速将安装到手机中的应用的Apk文件快速拿出来，使用下面几个ADB命令即可轻松做到。

<!--more-->

###### 查看是否链接到手机

```shell
adb devices
```

![image20220330225045870](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330225045870-16486596140232.png)



###### 进入手机的shell层

- 单一设备链接时

```shell
adb shell
```

![image-20220330225557489](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330225557489.png)

- 多设备链接时

```shell
adb -s 手机设备序列号 shell
```

![image-20220330225818186](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330225818186.png)

###### 查看安装软件的包名

- 查看所有软件的包名

```shell
pm list packages
```

![image-20220330230040400](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330230040400.png)

- 根据关键字查找包名

```shell
pm list packages | grep oneplus
```

![image-20220330230331065](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330230331065.png)

###### 查看安装包的位置

- 查看所有安装包位置

 ```shell
 pm list packages -f
 ```

![image-20220330230631200](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330230631200.png)

- 查看符合包名要求的安装包位置

```
pm list packages -f | grep tencent
```

![image-20220330231047522](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330231047522.png)

###### 将Apk拉到PC本地

```shell
exit
adb pull 上一步获取到的位置信息 PC存储位置(相对于命令行)
```

![image-20220330231534430](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330231534430.png)

PC 端文件(用户名文件下)

![image-20220330231658094](https://raw.githubusercontent.com/boatImpish/BlogImage/master/img/image-20220330231658094.png)
