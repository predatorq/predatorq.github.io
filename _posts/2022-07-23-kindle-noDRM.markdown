---
layout: post
title:  "kindle 退出国内市场，将购买书籍破除 DRM 本地储存"
date:   2022-07-23 
categories: kindle drm
---

## 起因

听闻kindle退出国内市场，想着如何转移泡面盖里的书籍。购入 KPW4 这几年里，看着书卖的便宜，天天优惠券，想着支持正版，买了不少书，最后成为了正版受害者。最开始想是能不能连同帐号一起转到美区去，最后发现是天方夜谭，于是尝试下载下来破除 DRM 后储存。因为网上没有找到较新的教程，于是决定自己写一下新的教程。

## 注意
- 本篇教程参考了两年前的这篇博客：[链接](https://thatinterpreter.net/kindle-drm/)，在此表达感谢。
- 如有其他疑问可以参照：[链接](https://github.com/apprenticeharper/DeDRM_tools/blob/master/FAQs.md)
- 破解后的文件请仅供个人使用，不要在网上传播，如有造成法律问题，本教程不负任何责任。

## 方法

- 下载calibre软件，我使用的版本为6.1。
- 下载DeDRM插件，因为原仓库停止维护，所以需要下载大佬fork后开发的新版插件，网址为[链接](https://github.com/noDRM/DeDRM_tools/releases)，在写这篇教程时为v10.0.3，可以支持calibre6。下载后将其解压。
- 在calibre软件中安装插件，位置在首选项 - 高级选项 - 插件 - 从文件加载插件，选择解压文件夹内的`DeDRM_plugin.zip`，加载完成按照提示重启。
- 下载kindle软件，需要特定版本。Windows下为`KindleForPC-installer-1.17.44170.exe`，Mac下为`KindleForMac-44182.dmg`，如果直接从kindle内导入会要求设备号等信息，且会使用KFX格式（需要安装其他插件），并且我经过尝试无法成功去除drm而使用kindle pc版不需要。其中Mac版为32位的，系统限制较大，建议使用windows。安装完成后注意关闭自动更新，调整安装目录（可选）。
- 将kindle书目下载，导入kindle中，直接导入即可，导入过程中DRM已经解开。建议一次全部下载，主要是kindle下载下来的文件名完全无法辨认。
- 现在就可以看到在calibre目录下的书籍了（noDRM）。