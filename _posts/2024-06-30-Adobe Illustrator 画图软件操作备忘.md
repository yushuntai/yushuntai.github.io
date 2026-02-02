---
layout: post
title:  " AI画图软件操作备忘"
date:   2024-06-30
tags: 实验方法与科研小技巧
categories: Front-end JavaScript
excerpt: 实验方法与科研小技巧
---


**目录：**

* content
{:toc}

## 快捷键
Alt+滚轮 放大和缩小 <br>
空格+鼠标左键 抓手拖动视野。 <br>
Ctrl+ Z 撤回； Ctrl+ S 保存； Ctrl+ shift + S 另存为；Ctrl+ 0 恢复原始尺寸；  <br>
选中图层 Ctrl+2 锁定图层，防止误触，点小锁 或者 Ctrl+Alt+2解锁； <br>
等比例缩放：按住shift拖拽对象可以等比例缩放对象。 <br>
F/Tab 键快速全屏 <br>


# 画韦恩图
## 叠加配色

画两个圆，然后设置透明度

<img src="/assets/images/Figure14.png" width="600">



此时交集区域为两种配色的叠加，通过透明度调整得不同叠加程度的韦恩图

## 指定配色

画两个圆，选中两个圆，点击形状生成器，点击填色，选中一种颜色，点击交集区域，此时交集区域被自由赋色

<img src="/assets/images/Figure15.png" width="600">

# 在AI中使用上下左右键无法移动形状或文字怎么办

是因为键盘增量太小了，调整键盘增量。

<img src="/assets/images/Figure16.png" width="600">

# 在AI中画箭头
<img src="/assets/images/Figure17.png" width="600">


# 如何画一个带箭头的半圆
<img src="/assets/images/Figure19.png" width="600">


# 如何将多串字符同时旋转

<img src="/assets/images/Figure18.png" width="600">

# 如何写基因的斜体
将字体改为Arial——Italic  
<img src="/assets/images/Figure20.png" width="200">


# 通过吸管改变描边颜色
<img src="/assets/images/Figure21.png" width="600">



**选择目标对象：** 使用选择工具（快捷键 V），点击你想要调整描边颜色的对象，使其处于选中状态。
**确保描边颜色框在前:** 在左侧工具栏中，找到颜色控制区域，有一个 填充颜色框（实心框）和一个 描边颜色框（空心框）。
确保描边颜色框在前。如果填充颜色框在前，可以按 X 切换，将描边颜色框置于前面。
**使用吸管工具吸取描边颜色：** 选择吸管工具（快捷键 I），然后按住 Shift 键。 使用吸管工具点击你想要的颜色，这样会将颜色应用到描边上，而不会影响填充颜色。


F/Tab 键快速全屏

# 如何画弹簧
先画一根直线，然后效果一一扭曲和变换-一波纹效果(Z)
<img src="/assets/images/Figure22.png" width="600">

# 如何输入蛋白结构分辨率——Å这个字符

按住 Alt 键，在小键盘上输入数字 0197即可，如果显示的是一个小方框，调整字体格式为Arial或其他字体格式即可。

# 输出的图片总是上面有一大片空白

<img src="/assets/images/Figure23.png" width="600">

（1）点到空白处——文档设置——编辑画板——将画板范围缩小
（2）文件——导出——导出为——**使用画板（U）** 勾上即可

# 如何将PPT中的图片高清晰度输出

文件——导出——另存为—— **增强型Windows元文件（*.emf）**——然后再把这个文件打开之后另存为TIF即可


## 如何输入蛋白结构分辨率——Å这个字符

按住 Alt 键，在小键盘上输入数字 0197即可，如果显示的是一个小方框，级的调整字体格式为Arial或其他字体格式即可。

## 如何多个图片一起裁剪

多张图片完整对齐——画上一个方框（随便怎样调整角度）——将该整体复制成多份——在每一份上分别删除其他图层——进行裁剪（如果想裁剪的位于第一图层，下面还压着两个图层，则将想裁剪的那个图层—“右键”——“排列”—“置于底层”——然后将上面的图层依次删除）

<img src="/assets/images/Figure24.png" width="600">

