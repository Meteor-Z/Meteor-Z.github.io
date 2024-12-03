# go

主要是学习go这门语言，

## 与其他语言的区别

个人认为与其他语言的区别

- 语法真的确实十分简单，感觉跟python差不多，但是更加的强类型
- 感觉go更加的面向过程而不是面向对象，也就是说更希望能提供一个函数，而不是提供一个.xxx()这样的方法

## 语法

跟其他语言不一样的，我放在这里，

- defer: 推迟计算，推迟的函数按照栈的先进后出来计算
  - 真好，lock的时候，可以使用defer推迟计算，
  - 不过好像go没有RAII保证直接unlock? 好奇怪
- 信道：感觉这玩意不错

## 相关链接

- [新手教程](https://tour.go-zh.org/list)
- [牛客go](https://www.nowcoder.com/discuss/616222020405092352)
- [github上的教程](https://github.com/xiaobaiTech/golangFamily)
- [Go](https://hj24.life/posts/%E5%85%AB%E8%82%A1%E6%96%87-go%E7%AF%87/)