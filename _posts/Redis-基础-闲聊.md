---
title: Redis-基础-闲聊
date: 2022-11-07 17:36:41
tags:
	- 对话
	- Redis
---

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
今天要不来聊聊Redis吧？
</div></div><br/>

<!--more-->

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
好
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
我个人是这样理解的：无论Redis也好、MySQL也好、HDFS也好、HBase也好，他们都是存储数据的地方
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
因为它们的设计理念的不同，我们会根据不同的应用场景使用不同的存储
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
像Redis一般我们会把它用作于缓存
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
当然啦，日常有的应用场景比较简单，用个HashMap也能解决很多的问题了，没必要上Redis
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
这就好比，有的单机限流可能应对某些场景就够用了，也没必要说一定要上分布式限流把系统搞得复杂
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/2022.11.07.17.43.04.png"/>
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
你在项目里有用到Redis吗？怎么用的？
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
Redis肯定是用到的，我负责的项目几乎都会有Redis的踪影
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
举几个项目用的案例？
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
嗯
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
我这边负责消息管理平台，简单来说就是发消息的
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
那发完消息肯定我们是得知道消息有没有下发成功的，是吧？
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
于是我们系统有一套完整的链路追踪体系
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
其中实时的数据我们就用Redis来进行存储，有实时肯定就会有离线的嘛（离线的数据我们是存储到Hive的）
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/008i3skNgy1gtyvevn728j60ko0fygm202.jpg"/>
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
对消息进行实时链路追踪，我这边就用了Redis好几种的数据结构
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
分别有Set、List和Hash
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
嗯….
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
我再稍微铺垫下链路追踪的背景吧
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
要在消息管理平台发消息，首先得在后台新建一个「模板」，有模板自然会有一个模板ID
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
对模板ID进行扩展，比如说加上日期和固定的业务参数，形成的ID可以唯一标识某个模板的下发链路
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
在系统上，我这边叫它为UMPID
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
在发送入口处会对所有需要下发的消息打上UMPID，然后在关键链路上打上对应的点位
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/008i3skNgy1gtyvfly3b7j60q205cglr02.jpg"/>
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
嗯，你继续吧
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
接下来的工作就是清洗出统一的模型，然后根据不同维度进行处理啦。比如说：
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
我要看某一天下发的所有模板有哪些，那只要我把清洗出来后数据的，将对应UMPID扔到了Set就好了
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
我要看某一个模板的消息下发的整体链路情况，那我以UMPID为Key，Value是Hash结构，Key是state，Value则是人数
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
这里的state我们在下发的过程中打的关键点位，比如接收到消息打个51，消息被去重了打个61，消息成功下发了打个81…
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/008i3skNgy1gtyvgkxib0j60pc066aac02.jpg"/>
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
以UMPID为Key，Hash结构的Key（State）进行不断的累加，就可以实现某一个模板的消息下发的整体链路情况
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
我要看某个用户当天下发的消息有哪些，以及这些消息的整体链路是如何
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
这边我用的是List结构，Key是userId，Value则是UMPID+state(关键点位)+processTime（处理时间)
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
嗯….
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
简单来说，就是通过Redis丰富的数据结构来实现对下发消息多个维度的统计
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
不同的应用场景选择不同的数据结构，再等到透出做处理的时候，就变得十分简单了
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
消息下发过程中去重或者一般正常的场景就直接Key-Value就能符合需求了
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
像bitmap、hyperloglogs、sortset、steam等等这些数据结构在我所负责的项目用得是真不多
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
要是我有机会去到贵公司，贵公司有相关的应用场景，我相信我也很快就能掌握
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/008i3skNgy1gtyvh1wbjoj60pk06w74l02.jpg"/>
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
这些数据结构底层都由对应的object来支撑着，object记录对应的「编码」
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
其实就是会根据key-value存储的数量或者长度来使用选择不同的底层数据结构实现
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
比如说：ziplist压缩列表这个底层数据结构有可能上层的实现是list、hash和sortset
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
Hash结构的底层数据结构可能是hash和ziplist
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
在节省内存和性能的考量之中切换
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
Redis还是有点屌的啊
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/008i3skNgy1gtyvhui46sj60py04ut9402.jpg"/>
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
就你上面那个实时链路场景，可以用其他的存储替代吗？
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
嗯，理论上是可以的（或许可以尝试用HBase），但总体来说没这么好吧
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
因为Redis拥有丰富的数据结构，在透出的时候，处理会非常的方便
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
如果不用Redis的话，还得做很多解析的工作
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
并且，我那场景的并发还是相当大的（就一条消息发送，可能就产生10条记录）
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
监控峰值命令处理数会去到20k+QPS，当然了，这场景我肯定用了Pipeline的（不然处理会慢很多）
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
综合上面并发量和实时性以及数据结构，用Redis是一个比较好的选择
</div></div><br/>

<div align="right"><div style="width: 80%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
<img src="/pictures/redis-基础-闲聊/008i3skNgy1gtyw0mlggbj60y405emy302.jpg"/>
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
嗯….你觉得为什么Redis可以这么快？
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
首先，它是纯内存操作，内存本身就很快
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
其次，它是单线程的，Redis服务器核心是基于非阻塞的IO多路复用机制，单线程避免了多线程的频繁上下文切换问题
</div></div><br/>

<div align="right"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent black; border-width: 10px; position: absolute; top: 10px; right: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent transparent transparent white; border-width: 10px; position: absolute; top: 10px; right: -19px"></span>
至于这个单线程，其实官网也有过说明（：表示使用Redis往往的瓶颈在于内与和网络，而不在于CPU
</div></div><br/>

<div align="left"><div style="width: 60%; border-style: solid; border-width: 1px; border-radius: 16px; position: relative; padding:30px; text-align:center"><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent black transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -20px;"></span><span style="width: 0px; height: 0px; border-style: solid; border-color: transparent white transparent transparent; border-width: 10px; position: absolute; top: 10px; left: -19px;"></span>
了解
</div></div><br/>
