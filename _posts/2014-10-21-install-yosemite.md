---
layout: post
title: 安装yosemite
category: posts
---
![yosemite_alt][yosemite]

1. 我是从10.9.5 mavericks升级到正式版本的10.10 yosemite。安装过程中进度条卡在“还剩余两分钟”半个多小时，强制重启了两次没有效果。在安装界面command+L查看安装日志，发现日志还在滚动说明安装程序应该没有问题。又等了大约半个多小时之后终于安装成功。后来搜索发现是因为homebrew和mactex的原因导致很多文件需要迁移耗费时间。
2. 顺利进入新系统。再次，需要重新[安装java](http://support.apple.com/kb/DL1572)。
3. 下载安装论坛版macpopo，可以正常使用，聊天历史记录如预期全部丢失。
4. 暂时没有发现其他异常，包括虚拟机vmware fusion都可以使用（去年升级10.9 mavericks的时候PD不兼容，改用了fusion）
5. [20141031更新]升级后一直很卡，忍了几天(码农本性。。)实在是受不了了，找了个空闲的时间排查了一下，发现罪魁祸首是--qq输入法，果断[卸载qq输入法](http://jingyan.baidu.com/article/67508eb4da3de99cca1ce437.html)，换用百度输入法后相当流畅。

[yosemite]: /images/yosemite.png "yosemite_ttl"
