---
title: 'masonry使用小结'
author: 'Meteor-Z'
date: '2025-07-20'
categories:
  - iOS
tags:
  - iOS
  - masonry
---

这周我开始使用了masonry，对于frame布局来说，很多地方确实不错，以下是开发的时候使用小结

## 多个View中间有间隔，并且想要居中

其实可以用一个parentView，将这些View放到parentView里面，然后让其"撑开",然后对parentView实现居中即可。

[]