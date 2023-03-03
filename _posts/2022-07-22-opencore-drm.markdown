---
layout: post
title:  "Opencore（Hackintosh）下的 DRM 问题"
date:   2022-07-22 13:22:16 +0800
categories: opencore drm
---

好奇opencore下的apple music无法播放无损，杜比，MV，所以去查了下。

## 参考方案
- 参考链接[FAQ of WhateverGreen](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.Chart.md)
- 可以看到在BigSur以上，无法使用intel核显开启DRM，如需要完美DRM，需要在bios中屏蔽核显并使用AMD的显卡

## 总结
- 台式机可以考虑iU+A卡的配置，其他的就别折腾了，特别是笔记本用户。
- 黑果可玩性越来越低，台式机还能折腾，如需要笔记本，还是买macbook，或是搞个win本装个linux（推荐arch系）。
- 可能safari无法播放网飞视频也是这个原因。