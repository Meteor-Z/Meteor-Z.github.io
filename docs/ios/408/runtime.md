# Runtime

oc运行时的相关面试题

## runtime面试第一题

```oc
@implementation Son: Father

- (instancetype) init {
    self = [super init];
    if (self) {
        NSLog(@"%@", [self class]);
        NSLog(@"%@", [super class]);
        NSLog(@"%@", [self superclass]);
        NSLog(@"%@", [super superclass]);
    }
    return self;
}
@end
```

会输出

```text
Son
Son
Father
Father
```

- oc的函数调用(发送消息)是发生在运行时期的，super和self唯一不同的是isa指针一开始执行的地方不同
  - self是直接从本类对象开始执行，然后一层层往上执行，
  - super是从父类开始执行
- class类比较特殊，是NSObject类自己实现的方法，其实这里self和super都执行到NSObject上了，找到同样的地点了，但是self这里内部执行的是objc_msgSend()方法，而super是objc_msgSendSuper()方法，这里虽然都找到了NSObject了，但是这里的参数有点特殊

- 在objc_msgSendSuper方法中，第一个参数是一个objc_super的结构体，这个结构体里面有两个变量，一个是接收消息的receiver，一个是当前类的父类super_class。
- objc_msgSendSuper的工作原理应该是这样的:从objc_super结构体指向的superClass父类的方法列表开始查找selector，找到后以objc->receiver去调用父类的这个selector。注意，最后的调用者是objc->receiver，而不是super_class，所以执行的还是self这个对象，然后self是Son，所以输出的就是Son。

- 其他：如果说父类实现了一个方法，那么调用的时候，其实就不同了，相当于子类执行了父类的方法。