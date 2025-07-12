---
title: 'ARM汇编'
author: 'Meteor-Z'
date: '2025-07-10'
categories:
  - iOS
tags:
  - iOS
  - 汇编
---

## 常用指令

- SVC：调一个系统调用


### 寻址

`LDR  W0, [X1]`

## 函数

- X0-X7放函数的参数，
- X0作为函数的返回值，如果是结构体的话，那么就将用X8兼容一下
- X19基本都是self,基本调一下

## 函数跳转

