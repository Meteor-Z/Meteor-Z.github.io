# 网站构建

本网站使用mkdocs进行构建，网上有很多资料可以借鉴，这里记录一下自动推送如何实现

所有的资源文件都在[此github链接](https://github.com/Meteor-Z/Meteor-Z.github.io)仓库的main分支上，然后bot将生成的文件推送到`gh-pages`这个分支上，然后github page选择`gh-pages`这个分支进行网页展示。

## 如何推送

github支持自动流水线，也就是action，可以查看[此链接](https://github.com/Meteor-Z/Meteor-Z.github.io/blob/main/.github/workflows/gh-deploy.yml)中的`gh-deploy.yml`进行书写，然后进行推送，同时，也应该将github page的配置选择`gh-pages`这个分支，否则上传不上去，

## 域名

网上也有，在docs/下创建CMAKE，然后在域名网站上配置指向的ip地址即可


