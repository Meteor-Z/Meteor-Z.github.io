# SDK

虽然说第三方库跟SDK是不一样的，但是SDK好听，所以还是用SDK吧

- 图片库：SDWebImage
- autoLayout库：marsony
- 日志库：CocoaLumberjack
- 网络库：AFNetWorking

## SDWebImage解决了什么痛点？

- 网络请求的时候因为延迟比较大，导致堵塞的时候会堵塞UI线程，导致界面流畅度卡顿，SDWebImage是异步的，可以很好的解决这一点
- 图片的传输是从网络上传输的，但是网络相当于一个延迟巨大的硬盘，可能会造成堵塞，导致图片加载不出来，SDWebImage就可以有一个站位图，站位图可以在图片请求不到的时候放上去
- 当网络请求得到数据后，网络上的数据已经和缓存到本地了，本地已经有这个数据了，可以不用再次网络请求，SDWebImage可以很好的解决这一点。

## masonry中的block为啥不用__weak?

- 这个Block是一个栈block，仅仅是使用一下，并没有造成循环引用，所以不需要__weak一下。