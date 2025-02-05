# objc面试题

## #include与#import的区别、#import与@class 的区别

- import相当于C/C++的防卫式声明，只会引入一次，但是inlcude不会解决这个
- @class相当于C++的前置声明，不需要知道具体实现，就可以使用对应的指针

## @public, @protocted, @private的作用

- 默认的好像是@protocted的访问权限
- @public是在任何地方可以访问
- @protocted是本类和子类相关访问
- @private仅允许本类访问
- @proterty属性提供的getter/setter说明属性是private的方法 存疑？？

## self = [super init]有什么作用？

- 子累要执行父类的构造函数，但是父类构造的时候可能出现错误，这里就是预防一下，进行容错

## oc中修饰成员变量的关键字有什么，都有什么作用？

- 原子操作
  - atomic：默认选项，原子操作
  - nonatomic: 非原子操作，不是原子操作的话，要加上这个
- assign：仅仅是简单的赋值操作，一般修饰简单的int，double，float等变量，其声明周期是栈进行管理的。如果修饰的是对象，可能就会出现内存泄露了。
- strong：强引用计数，被strong引用的不会析构，
- weak：不会持有对象，只是存储了对象的地址，如果说其他的strong的引用计数没有了，那么其weak就会自动将其变nil，防止不正当访问导致crash，
- copy，对对象进行一次深拷贝赋值，一般用于NSString，NSArray，NSDictionary这些。但是copy出来的都是不可变的，如果时Mutable的话，那么就会出现错误，切记！。

## 声明属性的时候使用NSString, NSArray, NSDictionary等要使用copy关键字，这是为什么呢？

- `copy`会复制一片全新的内存，然后用全新的指针去指向这片内存
- `strong`是一个指针去指向一个对象的内存地址，属于浅拷贝
- 如果使用`strong`那么可能其他地方去修改这些对象

## @property (copy) NSMutableArray *array 有什么错误？

- 注意，copy出来的东西一定是NSArray，只有mutableCopy出来的才是MutableArray的，也就是说，当复制的时候，在编译的时候是NSMutableArray，但是在运行的时候还是NSArray，那么在运行的时候就可可能出现错误

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