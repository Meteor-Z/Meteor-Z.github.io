# iOS基础知识

## MVC

- model: 处理相关数据，
  - UIBarButtonItem:
- View: 在屏幕中所看到的就是View
  - UITabBar
- Controller: 界面控制相关的，进行逻辑控制 
  - UITabBarController

## 基本框架

- UiWindow: 基础的UIView，只存在，展示一个UIWindow，
- storyboard ?
- WebView:
  - UIWebView: 不是很好，容易crash
  - WkWebView：独立进程/内存，crash不影响主进程

## 设计模式

- 委托设计模式， delegate，不懂原理，但是用起来不难,
  - 其实原理还是比较简单的
- 委托设计模式可以直接想象成，对于一个Cell，要将删除的内容交给他的Controller来删，然后delegate托管给Controller，然后执行对应的方法

## 组件

- UITableViewCell会有一个复用池，根据resuledifder作为标识
- 不显示在页面上的会放到池子里面，如果显示在页面上面就会从池子里面取出来
- UICollectionView更加强大，

## 文件存储

沙盒文件，这里直接进行隔离了，感觉比Android的隔离程度要高
