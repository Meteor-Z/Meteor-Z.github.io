---
title: 常用Tips
---

平时开发用的多的Tips，总结了以下

## Chiesl

```shell
touch .lldbinit
open .lldbinit
command script import /usr/local/opt/chisel/libexec/fbchisellldb.py
```

## Clang-Format

[gist链接](https://gist.github.com/Meteor-Z/47e1c73852e0ae3999403992a6349650)

## Git设置

```bash
git config --global user.name "meteor"
git config --global user.email "xxxxx@xx.com"
ssh-keygen -t rsa -C "上面的邮箱"
```

## Windows神秘代码

```bash
slmgr -ipk W269N-WFGWX-YVC9B-4J6C9-T83GX
slmgr -skms kms.0t.net.cn
slmgr -ato
```

## Windows相关问题

+ 换一个好用的梯子
+ utools上搜网络重置
+ 关闭网络代理后，在cmd上直接ipconfig /flushdns 来刷新缓存，很奏效

## MAC显示屏开启 HiDpi

```shell
bash -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```