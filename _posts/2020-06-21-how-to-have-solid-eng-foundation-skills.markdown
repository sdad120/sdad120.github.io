---
layout: post
title:  "怎么拥有最坚实的程序员基础技能？"
date:   2020-06-21 18:13:00 +0800
---
我一直又一个很大的疑问，程序员的很多工程经验需要来源于大量实践。但是传说中的程序员们却能年纪轻轻就开发出优秀的框架/系统。

Vue 来源于 Part time project
React 来源于 FB的一些有经验的程序员的智慧结晶
Kubernetes 来源于 Google的一些有经验的程序员的智慧结晶(甚至是非常长期的经验结晶)
Docker 来源于 公司作品
Linux 来源于

开源世界真的非常不一样，你的技术产品的经验来源全世界，而且有mutiplier的效果。

框架上的设计是指什么？

一个框架/库的核心理念是什么？

API上的设计？

Tech Designs怎么做？大家都会考虑什么点？

是不是有一些经典的东西可以keep in mind？

不一样的东西肯定有不一样的考虑，但是General是不是有什么可以总结一下

目标/目的是什么，怎么衡量这个项目成功了
在合理的general范围内，让更多人/团队受益

一个Service，我脑海里有什么要考虑的
- 数据从哪里来 -> 有什           
- 吞吐量，读和写
- -> 数据还要考虑增长
- 一致性要求
- 监控 -> Metrics & Alerts
- 维护，Scalability
- -> 我们有什么可以使用的工具/Service(内部/外部)
- -> 如果是一个General的方案，代码具体的安排，怎么做到扩展（Extensibility)
- -> 了解可能需要Integrate的东西/服务
- -> Security (Data Security)
- -> 好的Infra Team会给出Guideline教你选择Storage产品

比较大的不同可以看出来是考虑数据，数据存储

Tech Design时怎么决定要了解一个Service到什么程度？

[vue-doc]: https://www.youtube.com/watch?v=OrxmtDw4pVI
[jsconf-2013-react]: https://www.youtube.com/watch?v=GW0rj4sNH2w