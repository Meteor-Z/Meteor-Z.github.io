# 积累

## 文章

- [What every programmer should know about memory](https://zhuanlan.zhihu.com/p/611133924)（每一个程序员应该知道的内存知识）
- [C++服务编译耗时优化原理及实践](https://tech.meituan.com/2020/12/10/apache-kylin-practice-in-meituan.html)
- [git merge 和 rebase 的 区别](https://www.cnblogs.com/FraserYu/p/11192840.html)
- [for循环的时候要使用auto遍历的原因](https://www.zhihu.com/question/355171938/answer/899154458)
- [浮点数误差](https://zhuanlan.zhihu.com/p/673320830)  
- [markdown中mermaid的用法](https://soft.xiaoshujiang.com/docs/grammar/feature/mermaid/#e59bbee8a1a8e696b9e59091_7)
- [提问的艺术](https://zhuanlan.zhihu.com/p/20752519)
- [什么时候使用const_cast](http://blog.hostilefork.com/when-should-one-use-const-cast/)
- [为什么std::vector比std::list快](https://stackoverflow.com/questions/238008/relative-performance-of-stdvector-vs-stdlist-vs-stdslist)
- [加入const为什么可以优化代码(取模运算)](https://zhuanlan.zhihu.com/p/151038723)
- [测试oj网站的cpu, 好有趣](https://zhuanlan.zhihu.com/p/28322626)
- [gdb的实现原理](https://linux.cn/article-8943-1.html)
- [看懂火焰图，火焰图基本入门](https://www.ruanyifeng.com/blog/2017/09/flame-graph.html)
- [内存模型](https://zhuanlan.zhihu.com/p/382372072)
- [volatile和atomic的区别，以及volatile的应用](https://github.com/CnTransGroup/EffectiveModernCppChinese/blob/master/src/7.TheConcurrencyAPI/item40.md)
- [grpc的快速入门](https://grpc.io/docs/languages/cpp/quickstart/)
- [xmake编译选项](https://zhuanlan.zhihu.com/p/548735186)
- [C++零成本抽象](https://zh.cppreference.com/w/cpp/language/Zero-overhead_principle)
- 内存分配
  - [STL内存分配器](https://github.com/rongweihe/CPPNotes/blob/master/STL-source-code-notes/5%20%E5%8D%83%E5%AD%97%E9%95%BF%E6%96%87+%2030%20%E5%BC%A0%E5%9B%BE%E8%A7%A3-%E9%99%AA%E4%BD%A0%E6%89%8B%E6%92%95%20STL%20%E7%A9%BA%E9%97%B4%E9%85%8D%E7%BD%AE%E5%99%A8%E6%BA%90%E7%A0%81.md)
  - [malloc中的mmap和sbrk](https://sploitfun.wordpress.com/2015/02/11/syscalls-used-by-malloc/)
  - [了解 glibc malloc](https://sploitfun.wordpress.com/2015/02/10/understanding-glibc-malloc/)
- [4字节hash](https://burtleburtle.net/bob/hash/integer.html)

## 视频

- [性能优化 往数组里写入0为何比写入1更快？详解缓存的工作机制](https://www.bilibili.com/video/BV1gu41117bW)
- [git成熟项目的工作流](https://www.bilibili.com/video/BV19e4y1q7JJ/)
- [内存泄漏，以及为什么不要继承STL](https://www.youtube.com/watch?v=LKKmPAQFNgE)
- [https的原理，CA机构](https://www.bilibili.com/video/BV1uY4y1D7Ng)
- [UB行为以及相关后果](https://www.bilibili.com/video/BV1iF4m1L7MB)

## 书籍

- 深入理解操作系统(csapp)
  - 基本快读完了，但是还需要平时看看，
- 操作系统导论(ostep)
  - 文件系统里面不是很清楚，前面还行
- 程序员的自我修养(链接，装载和库)
  - 光看了前半部分
- 计算机网络(自顶向下方法)
  - 目前正在看
- 数据库系统实现
  - 目前正在看
- [EffectivModernCpp](https://github.com/CnTransGroup/EffectiveModernCppChinese/tree/master/src) 
  - 学些现代C++语法的
- 现代cpu性能优化与分析
  - 只有200页，但是信息量巨大
- Linux多线程服务端编程：使用muduo C++网络库
  - 陈硕的，非常不错
- STL源码剖析
  - 我觉得不错
- Windows核心编程
  - windows的工具书

## 博主

平时看看，可以爆一爆他的金币

- [陈硕](https://www.zhihu.com/people/giantchen) 博客好多东西，我都不懂，希望有懂得一天
- [zwx](https://github.com/zweix123/CS-notes)
- [韦易笑](https://www.zhihu.com/people/skywind3000)
- [双笙子佯谬](https://space.bilibili.com/263032155) 讲解c++视频的

## 网站

好用的网站都放在这了

- 绘图网站:
  - [Graph Editor](https://csacademy.com/app/graph_editor)
  - [draw.io](https://draw.io)
- 剪切板：
  - [godbolt](https://godbolt.org)
  - [在线剪切板](https://paste.nugine.xyz)
- c++
  - [cppreference](https://zh.cppreference.com/w/%E9%A6%96%E9%A1%B5) 手册
  - [cppinsights](https://cppinsights.io) 解糖用的
- [知乎](https://www.zhihu.com)
- [IEEE754计算](http://weitz.de/ieee)
- [c++ quick-benchmark](https://quick-bench.com/) 相当于一个benchmark
- [brpc网站](https://brpc.apache.org/zh/) 比grpc好多了，官方文档十分详细
- [Touying typst](https://touying-typ.github.io/touying/zh/) typst写相关ppt的，感觉非常不错

## 第三方库

- [backward-cpp](https://github.com/bombela/backward-cpp): 相当于gdb中的bt指令，可以在代码出现问题的时候打印出调用栈
- [fmt](https://github.com/fmtlib/fmt): 现代的C++格式化库，进入C++20标准里面了
- [compiledb](https://github.com/nickdiego/compiledb): 生成非cmake的clangd的json信息的
- [googletest](https://github.com/google/googletest): google的测试工具
- [benchmark](https://github.com/google/benchmark): 测试相关速度的
- [protobuf](https://github.com/protocolbuffers/protobuf): 传输序列化的
- [grpc](https://github.com/grpc/grpc) google的rpc调用