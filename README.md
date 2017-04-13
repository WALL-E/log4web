# log4web
通过http接口，允许JS把日志发送到服务器上，然后通过页面查看日志。

## 原则
* 不存储日志内容
* 页面不做认证
* 接口和应用分离

## 架构
Producer  ->  Broker  ->  Consumer

* Producer
  * https://github.com/houyhea/log4web
* Broker
  * OpenResty实现
* Consumer
  * AngularJS


## Broker实现

### 接口列表

* POST /apis/logs
  * 创建日志端点
* POST /apis/logs/{uuid}
  * 创建日志
* GET /apis/logs/{uuid}
  * 查看日志

### 日志存储
FIFO结构的存储模型
* Redis队列(v1)
* kafka
* Other

ref:[Redis实现简单消息队列](http://www.jianshu.com/p/9c04890615ba)

## Consumer实现
### 页面刷新机制
* 轮询(v1)
* Coment
* WebScoket

### 日志入口地址需要用户手动保存
