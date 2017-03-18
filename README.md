# UDP日志收集系统

## 模块介绍

### I/O模型
- 基于Netty的事件驱动的异步网络IO

### Redis缓存
- 使用Redis的简单使用的消息队列Pub/Sub模式，所有新日志条目进入队列，等待处理

### 持久化
- 准备使用 log4j2记录为文件，使用HDFS 进行存储

## 优势

1. 使用基于Java NIO的Netty，系统底层使用`epoll()`非阻塞忙轮询的I/O方式，加上UDP的传输方式，可以处理极高的并发数据
2. 使用Redis和HDFS，方便将缓存和文件存储做成分布式，提高负载上限
