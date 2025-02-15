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

- 变量如果说超出变量的作用域（生命周期停止）的时候就会release，但是如果放到autoreleasepool里面，那么这个对象就不会立即释放，会等到runloop休眠/超出@autoreleasepool作用域的时候才会被释放
- NSRunLoop对autorelasepool进行持有，然后控制对象的生命周期，在RunLoop循环一开始的是偶就会创建一个autoreleasepool，然后等到循环结束的时候，自动销毁释放池中的所有autorelease对象，
- 只要不废弃NSAutoleasePool对象（循环没有结束），那么生成的对象就不能被废除，那么可能就需要自己手动创建对应的autoreleasepool，减少内存峰值

### autoreleasepool实现原理

- 参考链接： [自动释放池的前世今生 ---- 深入解析 autoreleasepool](https://draveness.me/autoreleasepool/)

```c++
class AutoreleasePoolPage {
    magic_t const magic; // 完整性校验
    id *next; 
    pthread_t const thread; // 当前页所在的线程
    AutoreleasePoolPage * const parent; // 双向链表指向的上一个节点，起这个名字。。
    AutoreleasePoolPage *child; // 双向链表的下一个节点
    uint32_t const depth;
    uint32_t hiwat;
};
```

- 每一个AutoreleasePoolPage都是4096字节，其中一部分字节是他本身这个struct占用的字节，其他的都是他存储的对象 -> 用了一个id* 存储
- id*和本身的struct之间有一个nil的POOL_SENTINEL对象，当发送对应的消息的时候，就会一直popo，直到POOL_SENTINEL这个nil对象

### 小结

- 自动释放池由AutoreleasePoolPage 双向链表实现
- 对象调用autorelease的时候，会讲对象加入到AutoReleasePoolPage的栈中（上述的4096中不包括本体的部分）
- 调用AutoreleasePoolPage:pop会向栈中的对象发送release消息

## coreAnimation是什么

待补充

## C++空指针调函数会crash, OC调用方法却不会crash ,这是为什么

- 因为oc调用的时候本质是objc_msgSend()这个函数发送消息的，这个函数内部会判断self是否为nil，然后才会发送对应的消息

## main函数的含义

```oc
return UIApplicationMain(argc, argv, nil, NSStringFromClass([appDelegate class]));
```

- UIApplicationMain()函数，这个方法会为main thread设置一个NSRunLoop对象，应用可以在无人操作的时候休息，需要让它干活的时候又能立马响应。
  - 保证当前线程不会退出
  - 负责监听时间（触摸事件，网络事件等）
