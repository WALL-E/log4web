# log4web
通过http接口，允许JS把日志发送到服务器上，然后通过页面查看日志。

## 设计思路
* 客户端
  * https://github.com/houyhea/log4web
* 服务端
  * OpenResty实现


## 服务端

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

### 页面刷新机制
* 轮询(v1)
* Coment
* WebScoket

### 技术栈
* 开发平台
  * OpenResty
* 开发语言
  * Lua
