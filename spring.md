# Spring Notes

[![Author](https://img.shields.io/badge/author-chaohu-lightgrey.svg)](https://github.com/chaohu)

#### Instroduction
* IOC 控制反转
* Bean
* AOP

#### Source
* [http://spring.io](http://spring.io)
* [http://projects.spring.io/spring-framework](http://projects.spring.io/spring-framework)

#### How to use
Spring的注入方式
* 设值注入
* 构造注入

#### Bean的作用域
* singleton:单例，指一个Bean容器中只存在一份
* prototype：每次请求（每次使用）创建新的实例
* request：每次http请求创建一个实例且仅在当前request内有效
* session：同上，每次http请求创建，仅在session有效
* global session：基于portlet的web中有效（portlet定义了global session），如果是在web中，同session

#### Bean的生命周期
* define
* initial
* use
* destroy
