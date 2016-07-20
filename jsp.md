# jsp学习笔记

[![Author](https://img.shields.io/badge/author-chaohu-lightgrey.svg)](https://github.com/chaohu)

### 一、基础语法

#### jsp指令
* page指令：通常位于jsp页面的顶端，同一个页面可以有多个page指令
* include指令：将一个外部文件嵌入到当前jsp文件中，同时解析这个页面中的jsp语句
* taglib指令：使用标签库定义新的自定义标签，在jsp页面中启动定制行为

### 二、JSP内置对象及其常用方法

#### out
* void println():向客户端打印字符串
* void clear():清楚缓冲区内容，如果在flush之后调用会抛出异常
* void clearBuffer():清楚缓冲区内容，如果在flush之后调用不会抛出异常
* void flush():将缓冲区的内容输出到客户端
* int getBufferSize():返回缓冲区以字节数的大小，如果不设缓冲期则为0
* int getRemaining():返回缓冲区剩余多少可用
* boolean isAutoFlush():返回缓冲区满时，是自动清空还是抛出异常
* void close():关闭输出流



* request
* response
* session
* application
* Page
* pageContext
* exception
* config
