# Block面试题

## Block最最需要注意的是什么？

```oc
 // Block的循环引用
    __weak typeof(self) weakSelf = self; // 先声明一个weak，防止使用的时候循环引用
    [view showDeleteViewFromPoint:rect.origin clickBlock:^{
        __strong typeof(self) strongSelf = weakSelf; // 防止用的时候弄成nil
        [strongSelf.tableView deleteRowsAtIndexPaths:@[[strongSelf.tableView indexPathForCell:tableViewCell]] withRowAnimation:UITableViewRowAnimationAutomatic];
    }];
```

在非 ARC 的情况下，对于 block 类型的属性应该使用 copy ，因为 block 需要维持其作用域中捕获的变量。在 ARC 中编译器会自动对 block 进行 copy 操作，因此使用 strong 或者 copy 都可以，没有什么区别，但是苹果仍然建议使用 copy 来指明编译器的行为。

## Block用什么修饰

ARC下用strong和copy都可以，但是因为block有三种形式，全局，栈，堆，使用copy更好

## Block的实质

- [Block对象的捕获](https://github.com/pro648/tips/blob/master/sources/Block%E7%9A%84%E6%9C%AC%E8%B4%A8.md)

使用`clang -rewrite-clang main.m`可以将oc代码转换成C语言代码，关键代码如下

```c++
struct __block_impl {
    void *isa;  //isa指针，指向一个类对象，有三种类型：_NSConcreteStackBlock、_NSConcreteGlobalBlock和_NSConcreteMallocBlock

    int Flags; // block的负载信息(引用计数和类型信息)，按位存储
    int Reserved; // 保留变量
    void *FuncPtr; // 指向Block指向的代码块，执行的时候要执行的ptr
};

struct __main_block_impl_0 {
    struct __block_impl impl;
    struct __main_block_desc_0* Desc; // 此对象的的描述信息，就是有多大
    const char *fmt; // 多出的变量，也就是捕获进来的
    int val; // 这里直接就是捕获了，
    // 构造函数
    __main_block_impl_0(void *fp, struct __main_block_desc_0 *desc, const char *_fmt, int _val, int flags=0) : fmt(_fmt), val(_val) {
        impl.isa = &_NSConcreteStackBlock; 
        impl.Flags = flags;
        impl.FuncPtr = fp;
        Desc = desc;
    }
};

// Block要执行的函数
static void __main_block_func_0(struct __main_block_impl_0 *__cself) {
    const char *fmt = __cself->fmt; // bound by copy
    int val = __cself->val; // bound by copy
    printf(fmt, val); // 执行的函数
}

// 就是一个描述信息 
static struct __main_block_desc_0 {
  size_t reserved; // 保留变量
  size_t Block_size; // 下面的sizeof(struct __main_block_impl_0)
} __main_block_desc_0_DATA = { 0, sizeof(struct __main_block_impl_0)};
int main() {
    int dmy = 256;
    int val = 10;
    const char* fmt = "%d\n";
    // 这里相当于将函数传到到这个结构体里面，然后构造函数生成，然后再转换成void*，也就是这个block
    void (*block)(void) = ((void (*)())&__main_block_impl_0((void *)__main_block_func_0, &__main_block_desc_0_DATA, fmt, val));
    val = 2;
    fmt = "These values hahhaa val = %d\n";
    // 执行的时候在讲block转换回来，然后执行这个FunPtr...
    ((void (*)(__block_impl *))((__block_impl *)block)->FuncPtr)((__block_impl *)block);
    return 0;
}
```

- 奇怪，这里用到了C++代码，但是分明可以直接使用类lambda那样的实现原理去实现Block，但是为什么要弄成C的风格。。

### Block变量捕获

- 如果是普通变量，那么就直接捕获，相当于copy了一份
- static因为会存储在内存中，存储的是static对象的指针，然后用指针进行访问
- 全局变量，直接进行使用，因为全局都可以直接使用到

## Block区分的类型是什么

—— 涉及到对应的

## Block中什么时候才会循环引用

- 像AFNetWoring，Marsony这样的Block是不需要循环引用的
  - AFNetWorking是特殊处理的，所以不需要Block
  - Marsony看源码发现其实就是栈Block，没有被self持有
- 一般来说，self需要持有一个Block,然后Block中使用了self中的一个对象，然后才会造成循环引用，如果说一个Block不是self的一个属性，仅仅是使用了self中的相关属性，就不会造成循环引用
- 比较简单的例子就是A->B B->A这样的循环引用，如果是复杂的，那么就是A->B B->C C->A 这样的循环引用，所以要多加注意，不过我觉得所有的东西都要处理一下比较好
  - 注意一下：Block中使用self中的weak属性，是不会造成循环引用，因为就跟__weak self一样，是weak，但是我觉得每一次写__weak就比较好

## 如何读代码，如何快速进行定位。然后快速找到对应的代码

- 