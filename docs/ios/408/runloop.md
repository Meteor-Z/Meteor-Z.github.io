# RunLoop

## RunLoop的概念

其实就是类似于Windows 消息机制的EventLoop

- 如何管理事件/消息
- 如何在让线程在处理消息以休眠的形式以避免资源占用，同时在有消息来的时候立即被唤醒

## NSRunLoop和CFRunLoop的区别

- NSRunLoop是CFRunLoop（在CoreFoundation框架下）的api封装，提供了面向对象的api
- 前者是线程安全的，后者不是线程安全的

## CFRunLoop的数据结构


