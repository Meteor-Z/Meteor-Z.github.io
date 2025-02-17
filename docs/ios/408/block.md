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



