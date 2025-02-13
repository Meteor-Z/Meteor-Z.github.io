# Block面试题

## Block最最需要注意的是什么？

- 循环引用，在Block中使用self这样的对象的时候，很容易造成循环引用导致内存泄露等问题，解决方法如下：

```oc
 // Block的循环引用
    __weak typeof(self) weakSelf = self; // 先声明一个weak，防止使用的时候循环引用
    [view showDeleteViewFromPoint:rect.origin clickBlock:^{
        __strong typeof(self) strongSelf = weakSelf; // 防止用的时候弄成nil
        [strongSelf.tableView deleteRowsAtIndexPaths:@[[strongSelf.tableView indexPathForCell:tableViewCell]] withRowAnimation:UITableViewRowAnimationAutomatic];
    }];
```
