---
layout: post
title:  "部分三星NVMe固态在Opencore下的Trim问题解决"
date:   2022-07-21 13:22:16 +0800
categories: opencore trim ssd
---

## 问题说明
问题出现于三星的部分固态, 如:

- Samsung 950 Pro
- Samsung 960 Evo/Pro
- Samsung 970 Evo/Pro

可以参照[Github issue](https://github.com/dortania/bugtracker/issues/192)

在 opencore 黑苹果中无法使用 trim (trim boot时间较慢), 对应的表现为黑屏, 死机, 鼠标指针经常转圈等问题, 修复方法为关闭或调整boot时间.

## 修复步骤
- 更新Opencore至0.8.0以上, 似乎0.7.9和0.8.0有一定修复, (可以使用OCAT进行更新), 参考内容:
  - [reddit](https://www.reddit.com/r/hackintosh/comments/t8zi4s/how_to_opencore_078_079_differences/)
  - [insanelymac](https://www.insanelymac.com/forum/topic/351477-how-to-opencore-079-080-differences/)
- Bigsur及以下的修复方式:
  - SetApfsTrimTimeout设置为 0 (彻底关闭) 或 4294967295 (最长boot时间).
- Monterey系统限制设置时间无法生效只能使用0(彻底关闭).
## 注意事项
- 设置为 0 时系统报告显示trim开启, 实际上已经关闭, 可以参照[官方wiki信息](https://dortania.github.io/docs/latest/Configuration.html#quirks-properties2)
- 有条件还是换掉这几块固态比较好, 西数的几个系列支持比较好, 可以查看上方github issue.