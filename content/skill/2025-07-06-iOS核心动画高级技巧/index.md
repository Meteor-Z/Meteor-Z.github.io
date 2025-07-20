---
title: 'iOS核心动画高级技巧'
author: 'Meteor-Z'
date: '2025-07-06'
categories:
  - iOS
tags:
  - Object-C
  - iOS
  - 动画
---

## UIView和CALayer

CALayer是图层，仅仅是显示UI界面的，但是UIView包含的东西非常多，而且UIView的性能其实没有显示的性能影响，使用图层关联的视图而不是CALayer的好处在于，你能在使用所有CALayer底层特性的同时，也可以使用UIView的高级API（比如自动排版，布局和事件处理。

layer专门显示动画，绘图，因为macOS和iOS的绘图原理是相同的，但是接触方式是不同的（一个是鼠标点击，一个是触摸），所以这里将其分开，分别维护。比如说CGColorRef为什么有这个，是因为layer是QuartzCore框架，不是UIKit框架里面的。

> UIButton的继承：UIButton -> UIControl -> UIView -> UIResponder
> UUIControl是将复杂的触摸事件封装成了简单的易于使用的控件事件

### 什么时候使用CALayer而不是UIView

- mac OS上运行的跨平台程序
- 使用CALayer的子类
- 做一些对性能特别挑剔的工作，比如对UIView一些可忽略不计的操作都会引起显著的不同（尽管如此，你可能会直接想使用OpenGL绘图）

但是我觉得还是用UIView可能更加方便，因为视图和视图之间可能要添加，UIView可以很高的添加上去。

## 使用小结

### transform

transform伸缩变化的过程中，其实是对anchorPoint开始，然后开始伸缩变化，但是很多时候我想要将某一个组件从左到右开始伸缩，