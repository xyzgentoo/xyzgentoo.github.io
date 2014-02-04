---
layout: post
title: MacOSX右键菜单去重
category: mac
tags: [tip]
---


顺手留个记录，自己在mac上经常会碰到这个问题，右键打开方式中出现几个重复的，解决方法也很简单，主要是参考了大别的博客，具体的[文章链接在这](文章链接在这)

命令如下:

/System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/Support/lsregister -kill -r -domain local -domain system -domain user
***

这段代码的含义是，在本地，系统和用户空间上，重建LS数据库。

对于 lsregister 这个命令，我也多一句嘴，介绍下它的各个参数

-kill 重置全局LS数据库(最先执行)
-lint 打印详细应用程序文件关联注册中的错误信息
-convert: 将老数据库中的信息注册到新的LS数据库
-load: 加载LS插件
-lazy n: 指定一个注册等待时间
-r: 递归的查找文件夹内容以做关联之用（不包括pkg类型文件和隐藏文件夹下的内容）
-R: 递归的查找文件夹内容以做关联之用（包括pkg类型文件和隐藏文件夹下的内容）
-f: 强制更新所有对应注册信息
-v: 输出lsregister运行详细信息
-dump: 在注册完成后显示数据库内容

-h: 显示此帮助