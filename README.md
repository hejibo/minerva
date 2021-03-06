## Minerva

![智慧女神号](/minerva/conf/1.png "minerva")

Minerva(智慧女神号)旨在提供**简单可依赖的分布式数据定向抓取工具**,目前已经实现的抓取功能有:
+ 获取点评的POI数据(名称,地址,电话,城市,坐标)
+ 获取知乎的问题&答案

#### 特点
+ 使用redis存储linkbase信息:抓取url的FIFO队列由redis的list维护,已抓取url集合由redis的set维护
+ 页面解析存储在mongo,字段易存储、易扩展
+ spider可在多台机器单进程运行,充分利用机器资源
+ master和slave间方法调用采用Thrift RPC服务框架,效率高

#### Usage:
启动master: `python master.py`, 启动spider: `python spider.py`

#### Tips:
抓取知乎的信息需要输入账户,密码和验证码,如果cookie有效，则不用输入验证码

#### TODO:
+ 提升系统稳定性

#### 相关的依赖库:
+ pymongo (3.4.0)
+ redis (2.10.5)
+ thriftpy (0.3.9)
+ BeautifulSoup (3.2.1)
+ chardet (2.3.0)
+ requests (2.13.0)


