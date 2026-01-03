---
title: 'iOS调试'
author: 'Meteor-Z'
date: '2025-07-09'
categories:
  - iOS
tags:
  - iOS
  - 调试
---

## 常见的调试命令

```shell
expr 变量 | 表达式 // 显示变或者表达式的数值
expr -f h -- 变量 | 表达式 // 16进制格式显示变量或者表达式的数值
expr -f b -- 变量 | 表达式 // 二进制的形式
expr -i -- oc对象 // 等价于 po oc 对象
expr -P 3 -- oc对象 // 上面命令的加强版，会显示内部的数据变量的结构
expr my_struce->a = my_array[3] 赋值
expr (char*)_cmd // 显示某一个oc变量的方法名
expr (IMP)[self methodForSelector:_cmd] // 执行这个函数
p (IMP)[self methodForSelector:_cmd] // 打印出当前函数的地址
```

## 符号调试

在Xcode设置符号断点即可。

## 如何看某一个数值被XXX更改了，然后看回溯栈？

使用KVO进行注册，然后监控即可

## 多线程、网络的情况下，某一个对象的值好久没出来，如何进行测试

直接将对应的对象的地址打印到UILabel里面，然后将UILabel的数值显示到UI上，然后打日志，打印出当前的对象的地址，或者用Lookin看,查看当前的地址