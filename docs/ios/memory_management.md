# 内存管理

oc的内存管理其实跟C/C++差不多，其实很多东西都是相同的

## 原则

- 自己生成的对象，自己所持有，在自己不需要的时候，自己进行释放
- 非自己生成的对象，自己也能持有，但是自己不能进行释放

在MRC自己管理的情况下，是调用 release/autorelease/retain等方法管理生命周期，但是在ARC上，根据方法名称来进行管理的

根据以下名称进行分辨，以下是自己生成的对象，并且自己进行管理：

- `alloc`
- `new`
- `copy`
  - 要重写`NSCopying`方法，也就是实现`copyWithZone`这个协议
- `mutableCopy`

初次之外，其他的方法都是虽然自己能持有对象，但是自己不需要管理，也就是无法释放

## 如何实现非自己的对象也能保证释放

使用`releasepool`进行管理，对于`MRC`下的情况下，那么就需要以下

```objc
- (id)array {
    id obj = [[NSObject alloc] init];

    [obj autorelease]; // 在ARC下就不需要写这些了

    return obj;
}
```

直接交给autorelease就可以了，会在不用的时候进行释放。