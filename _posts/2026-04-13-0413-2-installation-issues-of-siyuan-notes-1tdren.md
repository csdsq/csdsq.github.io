---
title: 群晖部署思源笔记安装问题2项
date: '2026-04-13 21:06:29'
permalink: /post/0413-2-installation-issues-of-siyuan-notes-1tdren.html
layout: post
published: true
---





‍

以前在群晖里面安装的思源笔记看不到数据文件，所以最近就重新安装了一次，但是反复安装了几次都不成功，启动后总是提示错误。

最后才找到原因，特编制此文记录这2个问题。

‍

1、为什么看不到数据文件？

表现是思源笔记在群晖部署正常、使用也正常，但是进如docker文件夹里面的siyuan文件夹，看不到文档数据。

原因是笔记路径映射不对，所以解决办法就是重新安装，安装的时候设置正确的映射路径：

```
存储空间（映射文件夹）

添加文件夹 → 选择 `docker/siyuan/workspace`

装载路径：`/siyuan/workspace`
```

‍

2、为什么安装成功后反而总是启动不成功？

表现是安装成功，但是启动后总是频繁提示错误信息，无法正常启动。

原因是新版本的思源笔记要求安装的时候需要设置口令，但是实际上没有设置，所以才会出错。

解决办法就是在安装部署的事后设置口令，如下图，在命令栏位输入下面的代码，其中XXX位置就是口令，可以自定义，不限制位数。

```
-workspace /siyuan/workspace/ -accessAuthCode XXX
```

![01](https://blog.hser.ren/assets/20260416214901.png)

‍

‍

群晖部署思源笔记的详细教程可以查看这个链接：https://www.doubao.com/thread/w32f5426e839a14d4

‍

‍

‍
