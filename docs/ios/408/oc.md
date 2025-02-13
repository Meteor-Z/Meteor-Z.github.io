# oc面试题

## #include与#import的区别、#import与@class 的区别

- import相当于C/C++的防卫式声明，只会引入一次，但是inlcude不会解决这个
- @class相当于C++的前置声明，不需要知道具体实现，就可以使用对应的指针

## isKindOfClass、isMemberOfClass 作用分别是什么

- isKindOfClass方法的作用是判断一个对象是否为指定类或指定类的子类的实例，该方法会递归地向上检查对象所属的父类，直到父类为根类NSObject为止。(通过isa指针进行递归的判断)
- isMemberOfClass方法的作用是判断一个对象是否为指定类的实例。

## id对象有什么特性

- 没有*号
- 动态类型，也就是直接调用方法（发送任何消息）然后接收，不像C++一样，需要转换类型才能调用对应的方法
- 根据上条信息，所以是运行时期进行类型判断

## @public, @protocted, @private的作用

- 默认的好像是@protocted的访问权限
- @public是在任何地方可以访问
- @protocted是本类和子类相关访问
- @private仅允许本类访问
- @proterty属性提供的getter/setter说明属性是private的方法 存疑？？

## self = [super init]有什么作用？

- 子累要执行父类的构造函数，但是父类构造的时候可能出现错误，这里就是预防一下，进行容错
- 其实init的时候，一般都会这样做，C++默认是有的，没体现出来

## 声明属性的时候NSString, NSArray, NSDictionary等要使用copy关键字，这是为什么呢？

- `copy`会复制一片全新的内存，然后用全新的指针去指向这片内存
- `strong`是一个指针去指向一个对象的内存地址，属于浅拷贝
- 如果使用`strong`那么可能其他地方去修改这些对象，
- 如果时`Mutable`系列的画，那么就应该使用strong

## 声明属性的时候使用NSString, NSArray, NSDictionary等要使用copy关键字，这是为什么呢？

- `copy`会复制一片全新的内存，然后用全新的指针去指向这片内存
- `strong`是一个指针去指向一个对象的内存地址，属于浅拷贝
- 如果使用`strong`那么可能其他地方去修改这些对象

## oc中修饰成员变量的关键字有什么，都有什么作用？

- 原子操作
  - atomic：默认选项，原子操作
  - nonatomic: 非原子操作，不是原子操作的话，要加上这个
- assign：仅仅是简单的赋值操作，一般修饰简单的int，double，float等变量，其声明周期是栈进行管理的。如果修饰的是对象，可能就会出现内存泄露了。
- strong：强引用计数，被strong引用的不会析构，
- weak：不会持有对象，只是存储了对象的地址，如果说其他的strong的引用计数没有了，那么其weak就会自动将其变nil，防止不正当访问导致crash，
- copy，对对象进行一次深拷贝赋值，一般用于NSString，NSArray，NSDictionary这些。但是copy出来的都是不可变的，如果时Mutable的话，那么就会出现错误，切记！。

## 分类和类别有什么区别?

待补充

## 消息传递机制

待补充

## 关于autoreleasepool

待补充

## coreAnimation是什么

待补充