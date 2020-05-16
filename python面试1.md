# python面试1

面试技巧
python语言篇
算法与数据结构篇
编程范式
操作系统篇

网络编程篇
数据库篇
web框架篇
系统设计篇
面试经验篇


# 面试流程分析


```
岗位职责（业务是否感兴趣）
职位要求（自己是否掌握，查漏补缺）
公司技术栈（公司用到哪些技术）

```

## 头条招聘


```
负责程序化投放，冷启动，用户激励等核心系统的开发和优化
海量数据和分析技术理解
完成跨部门紧密合作


招聘要求：
算法，数据结构
python
web开发组件--mysql,redis,hbase ,mongo,db,nosql,kafaka,thift原理和使用场景
http,web安全


```
## 面试流程和环节


```
学生重基础，社招重项目
一面：问基础，计算机理论基础，算法
二面：项目 做了哪些项目，实现的技术栈，担任了哪些职责
三面：设计 如何实现简单的账号系统，如何实现feid流经验

学历和成绩
大学所学计算机课程
在校项目，实习经验

参加哪些项目
职责
系统设计经验
从0搭建简单的项目，灵活的使用组件
行为面试：
自我介绍
口头表达能力
沟通交流能力

hr面试：
薪资待遇
职业规划
自我介绍、沟通交流


```
## web请求的流程


```
浏览器--负载均衡-web框架--业务处理-数据库缓存

后端技术栈：
python基础：
语言特定：编译，解释
语法基础：
高级特性：装饰器
算法数据结构
分析时间和空间复杂度
常见的数据结构和算法

操作系统
常用liunux命令
进程，线程
内存管理

网络编程：
常用tcp/ip http
socket编程基础-异步框架
python并发库--rust,go

数据库：
mysql,索引优化，常考
nosql的使用场景
redis缓存，常见的数据类型
zset 排序，redis设计与实现

python web框架
常用框架对比，retful
wsgi原理
web安全问题，sql注入，xss

系统设计：
设计原则，如何分析
后端常用组件（缓存，数据库，消息队列）
技术选型和实现（短网址服务，feed流系统）

技术之外：软实力
学习能力
业务理解能力，沟通交流能力
心态

python初、中级工程师技能要求：

初级工程师：
计算机理论基础
代码规范，风格良好
能在指导下靠谱地完成业务需求。


中级工程师：
计算机基础，丰富的项目经验
独立设计完成项目需求
熟悉常用的web组件（缓存，消息队列等），具备一定的系统设计能力

软实力：
具备产品意思，技术引导产品
沟通交流能力，团队协作能力
技术领导能力和影响能力

面试找核弹，工作拧螺丝
工作内容和业务紧密相关
平台决定成长（业务体量）‘
准备面试需要有的放矢，

简历内容，突出关键信息
基本信息
职业技能
关键项目经验

简历自我评价：
可有可无
最终面试官评价
内容简洁，态度真诚

简历加分项：

知名项目经验
技术栈比较匹配
开源项目（github/技术blog/linux/unix )

学习加练习，输出加总结

自我介绍：
你好，我叫xx,毕业于xx,所学专业xx
之前就职于xx公司，担任后端工程师，负责xx项目，对xx技术比较熟悉
我的工作经验和目前这个岗位较为匹配，希望能投应聘到这个岗位

行为面试和回答技巧：

```

# python语言基础考察点


```
python是动态强类型语言
动态值得是编译期间还是运行期确定类型
强类型值得是不会发生隐士类型转换

有点和缺点：
胶水语言，轮子多，应用广发
语言灵活，代码维护问题，python2/3兼容问题

鸭子类型：
关注点在对象的行为，而不是类型
file/stringio/socket--read/write--file lile 
猴子补丁：
什么：运行时属性替换。
哪些地方：gevent 库需要修改内置的socket
from gevent import mongkey ; monkey.patch_socket

import socket

print(socket.socket) # 内置的socket

print("after monkey pathc")
from gevent import monkey
monkey.patch_socket() # gevent 的socket
print(socket.socket)

import select
monkey.patch_select()
print("after monkey path ")
print(socket.socket)


import time
print(time.time()) # 打印time的内置函数

def _time():
    return 124

time.time = _time

print(time.time()) # 打印自定义的_time

自省：
运行时判断一个对象的类型的能力
python 一切皆对象，用type , id isinstance 

#  自省

ll = [1,2,3]
d = dict(a=1)

print(type(ll))
print(type(d))

print(isinstance(ll,list))
print(isinstance(d,dict))

def add(a,b):
    if isinstance(a,int):
        return  a + b
    elif isinstance(a,str):
        return a.upper()+b

print(add(1,2))
print(add("head","world"))

print(id(ll)) # 返回变量在内存中的地址
print(id(d))

print(ll is ll) # is = 的区别
print(ll is d ) # is 判断id是否相同

列表和字典推导：
print([i for i in range(10) if i% 2 == 0 ])

#  一种快速生成list/dict/set 的方式， map,filter
print((i for i in range(10) if i%2 == 1)) # 生成器,节省内存


# zip 成对的叠对a 和b

a = ['a','b','c']
b = [1,2,3]

# print(zip(a,b))
c = zip(a,b)
print({k:v for k,v in c })
print(type(c))


如何编写python,禅道

import this 
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

python2/3 差异常考题

print函数--p3
print关键字-py2

编码问题：
除法变化--py3--小数


```
