---
layout: post
title: iOS高级程序员10道面试题
category: ios
tags: [ios,interview]
---

本文的主要内容来自我在[onevcat.com](http://onevcat.com)上看到的一篇文章，其中就列出了10个面向iOScocoa程序员的技术问题，问题本身没有标准答案，都是开放型的，在这里我也做个收录。

其实我也写了iOS程序近3年，有些东西也没有特别静下心来好好研究研究，也算是对自己cocoa知识结构的一个考察吧

下面就进入正题
---

* 你使用过Objective-C的运行时变成(Runtime Programming)么？如果使用过，你用它做了什么？你还能记得你所使用的相关的头文件或者某些方法的名称么？

* 你实现过多线程的Core Data么？NSPersistentStoreCoordinator, NSManagedObjectContext, NSManagedObject中的哪些需要在线程中创建或者传递？你是用什么样的策略来实现的？

* Core开头系列的内容。是否使用过Core Animation和Core Graphics。UI框架和CA，CG框架的联系是什么？分别用CA和CG做过些什么动画或者图像上的内容。（有需要的话，还可以设计Quartz的一些内容）

* 是否使用过Core Text或者Core Image等？如果使用过，请谈谈你对Core Text或者Core Image的体验。

* NSNotification和KVO的区别和用法是什么？什么时候应该使用通知，什么时候应该使用KVO，它们在实现上有什么区别么？如果用protocol和delegate（或者delegate的NSArray）来实现类似的功能可能么？如果可能，会有什么潜在的问题？如果不能，为什么？

* 你用过NSOperationQueue么？如果用过，你为什么要使用它？请描述它和GCD的区别和类似的地方（提示：可以从亮着的实现机制和适用范围来描述）

* 在使用GCD以及block时，要注意些什么？他们俩是一回事么？block在ARC中和传统的MRC中的行为和用法有没有什么区别，需要注意些什么？

* 你是否做过异步的网络处理和通讯方面的工作？如果有，能具体介绍一些实现策略么？

* 对于Objective-C，你认为它最大的优点和最大的不足是什么？对于不足之处，现在有没有可用的方法绕过这些不足，来实现需求。如果可以的话，你有没有考虑重新实现OC的一些功能？如果有，具体会如何做？

* 你实现过一个框架或者库以供别人使用么？如果有，请谈一谈构建框架或者库时候的经验；如果没有，请设想和设计框架的public API，并指出大概需要如何做，需要注意一些什么方面，来使别人容易地使用你的框架。

以上这些问题，对于技术积累会是一个很好的考察，因为如果没有对这些问题中涉及的内容有过实际使用和体会的话，是很难较完整和全面回答这些问题的。

在为团队寻找高级别研发工程师或者leader的候选人时，这些问题的回答会是对应聘者技术深度和广度的一个有效考察。

---

p.s. 下面是我自己对部分上述问题的笔记，也算是以后可以做个参考

## 部分讨论

#### Objective-C优缺点

##### 优点
* Classes are objects
* Dynamic typing
* Categories
* Message sending
* Runtime

##### 缺点
* 不支持namespace
* 不支持运算符重载
* 不支持多重继承
* 使用runtime，所有的方法都是函数调用 - 不支持编译时性能优化，如inline函数，常量传播等

#### 关于框架
我打算好好研究一下ASIHTTPRequest，一来这是一个网络请求相关的库，里面涵盖了多线程，网络等相关领域的应用，二来这个库被广泛应用，太多的项目依赖于它，三来这个库的作者已经不维护了，了解透彻后，也许可以为它的发展贡献些代码