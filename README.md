# toktik-demo

## 第六届字节青训营项目

## 软件架构

本项目采用服务架构，使用consul作为注册中心，kitex框架搭建。分为用户、通信、对象存储、网关、视频五个部分。
其中网关部分使用hertz搭建。 文件存储使用腾讯云对象存储。视频封面在上传视频后自动生成。为了加快访问速度，
还使用了cdn技术加速访问。


## 必要使用环境安装
+ 安装mysql数据库（[安装教程](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)），或者使用兼容mysql的云数据库。
+ 安装consul（[安装教程](https://developer.hashicorp.com/consul/downloads)） 测试

## 项目结构
```
|
|-- bin             // 编译后程序的可运行文件    
|-- cmd             // 一些启动、关闭的命令
|-- config          // 程序的配置文件
|-- log             // 程序的运行日志
|-- service         // 服务主体文件夹
|      |-- cos      // 文件上传微服务，主要负责将文件上传至对象存储
|      |-- message  // 消息微服务，主要负责好友之间的消息传递
|      |-- user     // 用户微服务，主要负责用户相关的功能，包括注册登陆、关注等
|      |-- video    // 视频微服务，主要负责视频相关的功能，包括投递视频、获取视频列表、视频的点赞评论等
|      |-- web      // 网关微服务，主要负责接收网络请求并进行数据处理
|-- sql             // 建表的SQL语句
|-- thrift          // 定义的接口文件
```
