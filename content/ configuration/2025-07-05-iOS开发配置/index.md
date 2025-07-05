---
title: 'iOS开发配置'
author: 'Meteor-Z'
date: '2025-07-05'
categories:
  - iOS
tags:
  - iOS
  - 开发配置
---

## 软件

- 超级右键
- Xcode
- [HomeBrew](https://brew.sh/zh-cn/)
- [RVM](https://rvm.io/)
  - 安装命令：`rvm install ruby-3.1.7 --with-openssl-dir=$（brew --prefix）/opt/openssl@1.1`


## Terminal

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

plugins=(git zsh-syntax-highlighting zsh-autosuggestions sudo)
```

### 软件安装

```shell
brew install 
```