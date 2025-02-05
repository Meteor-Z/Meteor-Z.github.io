# Block

## 注意事项

在Block中，如果使用self的话，会导致Block对象捕获self这个对象，这样就可能会造成循环引用，所以这里一定要注意，标准如下：

```oc
 // Block的循环引用
    __weak typeof(self) weakSelf = self; // 先声明一个weak，防止使用的时候循环引用
    [view showDeleteViewFromPoint:rect.origin clickBlock:^{
        __strong typeof(self) strongSelf = weakSelf; // 防止用的时候弄成nil
        [strongSelf.tableView deleteRowsAtIndexPaths:@[[strongSelf.tableView indexPathForCell:tableViewCell]] withRowAnimation:UITableViewRowAnimationAutomatic];
    }];
```
