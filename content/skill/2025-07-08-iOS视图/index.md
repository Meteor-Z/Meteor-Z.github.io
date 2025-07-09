---
title: 'iOS视图'
author: 'Meteor-Z'
date: '2025-07-08'
categories:
  - iOS
tags:
  - iOS
  - 视图
---

## setNeedsLayout VS layoutIfNeded

- `setNeedsLayout`会调用`layoutSubViews`方法，对于子视图进行重新布局
- 限频？

## setNeedsDisplay

- `setNeedsDisplay`是异步执行的，自动调用`drawRect:`方法
- [什么时候需要在 iOS 中调用 setNeedsDisplay？](https://stackoverflow.com/questions/10818319/when-do-i-need-to-call-setneedsdisplay-in-ios)
  - 就是覆盖了drawRect的时候，才需要这个方法，日常的UI界面已经涵盖了这个方法了，就是已经帮你实现了drawRect了，不需要重写了
