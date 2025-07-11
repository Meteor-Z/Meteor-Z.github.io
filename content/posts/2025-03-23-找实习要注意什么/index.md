---
title: '找实习要注意什么'
date: '2025-03-23'
categories:
  - 实习
tags:
  - 实习
---

- 现在学弟们都开始找实习了，遂根据我的找实习的经历，写一篇关于找实习的文章
- 当然，以下更多是关于计算机专业的。其他专业也可以参考参考
- 以下内容纯属个人见解，仅仅是希望给大家提供一份帮助，如果有不同意见，欢迎一起讨论。

## 投递相关

定要海投，对于大部分来说（尤其像我一样，四非学历），不是想去哪一个公司就去哪一个公司的，面试的时候有很大的除技术之外的运气成分，所以一定要海投，要所有的公司都要投递一遍，可以打开Boss直聘这样的软件，然后猛猛投递，有面试的话，就开始面试，面过了再选。

在水群的过程中，我发现学弟投递简历的时候更想要投递小厂，对大厂比较畏惧，可能是因为技术难度等方面有点高，所以说畏惧投递大厂。但是，大厂之所以是大厂，不光是因为薪资待遇比小厂的要好，更重要的是大，他招的人多啊，招收的人多代表有更多的机会，而且很多厂是可以面挂重新捞人的，所以说，这个不要担心。

## 面试流程

一般互联网公司是（2 或者 3 + 1面，也就是2到3次技术面 + 1次hr面

- 网上投递：
  - 主要是官网和内推
  - 官网：直接在各大厂的官网上投递，如果不知道什么公司可投，可以看牛客上别人投递的公司
  - 内推：找别人的内推码，填上去，虽然可能用处不大，但是肯呢个还是有一点作用。（最主要的是你进公司了，内推你的人有米赚（bushi.
- 技术面：
  - 对于一面来说，大概率是你面试的组的一个员工来面试，相对来说，面试的时候，比较简单，侧重于面试的计算机八股 + 基础知识，只要准备好，过的概率还是非常高的
  - 二面大概率是你的ld了，也就是这个组的组长，面试的时候侧重于你的项目水平，要求更高，对于项目方面一定要准备好，我在二面翻车的几率非常高，几乎都是二面挂的
  - 如果有三面，那么可能是你的+2，在我的面试情况中，跟二面的相关内容是差不多的，好好准备就行了。
  - 当然，以上是大概率，也有可能不是，比如对我来说，有一次面试一面二面是同一个人，还有一次一面是我的导师，二面就是我的+2了（ld的ld）。
- hr面： 基本就是问你的个人情况，基本问题不大，如果你在hr面挂了，可能就是因为被排序，有人面的比你更好所以挂了。

## 必要技能

### 技术

众所周知，面试的时候，虽然有一部分运气因素之外，但是最重要的还是自己的技术水平，以我为例，实习和校招的面试的时候，因为我的岗位不同，所以考察了一下内容

- 计算机网络/操作系统
  - 这些就比较多，具体可以看各大博主整理的相关资料。
- 各个语言的基础知识，：
  - 如C++中的虚函数表，sizeof一个类是多大，inline是干什么的。这些基础问题
  - 如果是其他的Java语言，也有对应的面试题
- 项目：
  - 你的项目的效果是什么，为什么选择这个项目，有什么量化指标，你在做这个项目中遇到了什么问题，这个问题你是怎么解决的。
  - 根据你选择的岗位不同，可能考察的也会有所不同
  - 比如我在面试的时候，考察过Windows相关的知识点，比如说COM编程，MFC，DLL相关,Dump文件，WinDbg调试相关，也考察过汇编，读相关汇编，然后看这段代码的意思等问题。如果是其他岗位，可能就没有这些问题。

### 算法题

- 其实大部分厂的算法题不是那么难，认真准备还是能写出来的，其主要出的都是链表题，主要是leetcode上面的hot100题目，在面试前最起码都过一遍，最好是能功利一点，能'背'下来，这个背是加引号的背，因为面试的时候紧张 + 时间短，不像打acm一样，有五个小时的时间，这个时间很短的，所以要看到题目，就能直接写出来是最好的。
- 另外，笔者自己是打acm的，一般是用C++写题，这时候很多ap(acm批，简称ap)就喜欢#define <bits/stdc++.h> 然后直接 using namespace std; 我认为这个在面试的时候，是非常不好的，因为面试官没有打过算法竞赛，而且会看你除了算法题写的对不对，还有你在写算法题的时候的工程化，规范化。按照写工程的思路去写算法题。
  - 不要使用万能头文件和using namespace std;
  - 写代码的时候要有缩进，要规划化。
  - 代码命名要更加的准确，起一个int类型的名称的时候int size 都比 int a 这样的命名好。
  
题外话：我第一段实习结束的时候，我问了我的导师（也就是我一面面试官），为什么当时把我招进来，他说：看你在大学的时候打了这么多比赛，拿了挺多奖，面试的时候代码写的也挺好的，所以就要你了，泪目，这是我大三下找实习中为数不多的面试中唯一过的面试，然后就去实习了。

## 沟通能力

面试本质上就是沟通。是你选择这家公司，然后公司选择了你，是一个双向选择的过程。如果你的技术很好，那么在面试的时候无法表达，无法将你想要表达的信息传递给面试官，面试官觉得驴唇不对马嘴，也是不行的，这是我面试的时候，某一个面试官在我知乎上留的相关言论，也作证了这个观点，同样，在工作的时候，沟通能力也是非常有必要的，如何正确表达，是非常重要的。对此我觉得有以下建议：

- 面对一道问题的时候，自己将要表达的内容说出来，然后看相关内容是否流畅，是否清晰，能否正确表达出来。因为有心里面想的，说出口可能就出错了，这个要在面试前好好准备
- 专业术语一定要表达清楚，以我为例，有一次私钥和公钥这些专业术语就没记住，其实自己是知道的，但是面试的时候可能会突然紧张，突然就忘记了，所以这个也要好好准备。
- 一定要流畅表达，可能面试官是不懂你这个的，但是可以通过的你的表达，看你是否是真的掌握这个，（自己掌握的和心虚的还是有差别的，（其实就是唬住面试官。

题外话：我自己的沟通水平简直是一tuo,很多东西也无法表达清楚，可能这篇文章也是如此qwq，实习结束的时候，ld也对我语重心长的说在以后得职业生涯中，提高提高自己的沟通能力，真的泪目┭┮﹏┭┮。

面试成功的因素不光有以上原因，可能还有对应的运气成分，面试失败不要紧，从面试中吸取教训，多复盘，多面试，好好准备下一次面试。

## 其他话术

面试的时候有很多话术，比如说你能否马上到岗实习，能实习多长时间，对于这个，要尽量答应对方的要求，比如说实习六个月，你就说实习六个月以上，即使你不能实习六个月以上，你也要说，你要确保你先过这个面试，然后再选，虽然有点不仁道，但是确实这样的。一定要确保你面试过了，将主动权掌握在自己的手上，然后再选。
