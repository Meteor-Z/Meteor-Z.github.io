# objc面试题



## obje中的isa指针指向的是什么，有什么作用？

- isa指针其实是一个结构体，当前对象的isa对象指向当前类，当前类的isa指针指向他的父类，父类指向他的父类，最终指向NSObject，NSObject最终指向他自己，因为oc是动态类型的语言，在调用方法的时候会用isa指针来找相关的方法调用。

## 描述一下RunLoop

- [深入理解RunLoop](https://blog.ibireme.com/2015/05/18/runloop/)

## 描述一下RunTime

- [RunTime入门](https://www.ianisme.com/ios/2019.html)

## 其他

- [面试题](https://github.com/josercc/iOS-Interview/blob/master/Objective-C%E9%9D%A2%E8%AF%95%E9%A2%98.md)
- [面试题](https://www.nowcoder.com/discuss/353153872283770880?sourceSSR=search)
- [github链接](https://github.com/joy0304/Joy-Blog)