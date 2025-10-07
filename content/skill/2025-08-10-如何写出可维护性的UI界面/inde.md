---
title: '如何写出可维护性的UI界面'
author: 'Meteor-Z'
date: '2025-08-10'
categories:
  - iOS
tags:
  - iOS
  - UI界面
---

UI界面是随意可变的，其内部的数据无时无刻都在变化，因为数据的变化可能会导致UI界面的变化，我们既要UI界面能够流畅运行，又要能够使得UI界面是可维护的，那么应该怎么做呢？

## AutoLayout和Frame布局

iOS无非就两种布局，一种是绝对布局，基于frame的形式，另一种是相对布局，基于autolayout的形式，并且使用最多的还是masonry，在我用的过程中，有以下优点和缺点。

## AutoLayout布局

现在在项目开发的时候，我几乎都是使用autoLayout布局，因为写起来比较舒服，虽然性能不是很好，但是写起来快，代码看起来整洁，易于维护。在autolayout布局中，有这么几个函数比较关键。，

```object-c
- (void) setNeedsUpdateConstraints;
- (void)updateConstraints;
```

其中，自动约束的视图应该放在`updateConstraints`中进行更新，

### AutoLayout注意的点

- 在`updateConstraints`的官方文档中注意到`[super updateConstraints]`应该放在最后一行。

## Frame布局

frame布局对应的函数也有两个对应的函数

```object-c
- (void)layoutSubviews;
- (void)setNeedsLayout;
```

### Frame注意的点

- 在`layoutSubviews`中，因该提前使用`[super layoutSubviews]`，
