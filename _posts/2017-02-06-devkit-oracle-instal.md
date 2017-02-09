---
title: oracle安装详细步骤
layout: post
guid: urn:uuid:a15b6dfb-956d-4e66-b40f-6d6fee5d673c
tags:
  - oracle
  - devkit
---

### Oracle简介

> ORACLE数据库系统是美国ORACLE公司（甲骨文）提供的以分布式数据库为核心的一组软件产品，是目前最流行的客户/服务器(CLIENT/SERVER)或B/S体系结构的数据库之一。  
作为一个关系数据库，它是一个完备关系的产品；作为分布式数据库它实现了分布式处理功能。但它的所有知识，只要在一种机型上学习了ORACLE知识，便能在各种类型的机器上使用它。

#### 名词释义

> **关系型数据库：**关系数据库，是建立在关系模型基础上的数据库，借助于集合代数等数学概念和方法来处理数据库中的数据。现实世界中的各种实体以及实体之间的各种联系均用关系模型来表示。关系模型是由埃德加·科德于1970年首先提出的，并配合“科德十二定律”。现如今虽然对此模型有一些批评意见，但它还是数据存储的传统标准。标准数据查询语言SQL就是一种基于关系数据库的语言，这种语言执行对关系数据库中数据的检索和操作。 关系模型由关系数据结构、关系操作集合、关系完整性约束三部分组成。

> **分布式数据库：**将原来集中式数据库中的数据分散存储到多个通过网络连接的数据存储节点（计算机）上，位于不同地点的许多数据存储节点（计算机）通过网络互相连接，共同组成一个完整的、全局的逻辑上集中、物理上分布的大型数据库。

### 工具

> oracle安装包下载地址：  
百度网盘：[http://pan.baidu.com/s/1minuD9u](http://pan.baidu.com/s/1minuD9u)  
官网地址：[http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html)  
打开链接可以看到  
![Shadow](/media/files/2017/02/06/ks_000.png)  
在如图位置点选*Accept License Agreement*  
![Shadow](/media/files/2017/02/06/ks_002.png)  
选择对应操作系统下的Oracle程序包下载  
![Shadow](/media/files/2017/02/06/ks_003.png)  
下载完成，有的是一个压缩包有的是两个压缩包  
![Shadow](/media/files/2017/02/06/ks_004.png)  

### 安装步骤

> #### 解压下载的压缩包中的文件到一个文件夹中  
![Shadow](/media/files/2017/02/06/ks_005.png)  
#### 解压后文档结构如图所示  
![Shadow](/media/files/2017/02/06/ks_006.png)  
#### 双击steup.exe，进入安装界面  
![Shadow](/media/files/2017/02/06/ks_007.png)  
选择安装Oracle主目录位置，输入数据库口令，点击下一步  
![Shadow](/media/files/2017/02/06/ks_008.png)  
点击下一步，可以看到  
![Shadow](/media/files/2017/02/06/ks_009.png)  
选择是  
![Shadow](/media/files/2017/02/06/ks_010.png)  
点击安装，耐心等待  
![Shadow](/media/files/2017/02/06/ks_011.png)  
![Shadow](/media/files/2017/02/06/ks_012.png)  
![Shadow](/media/files/2017/02/06/ks_013.png)  
最终看到  
![Shadow](/media/files/2017/02/06/ks_014.png)  
![Shadow](/media/files/2017/02/06/ks_015.png)  

### 服务启动与关闭  
> #### 右键点击我的电脑 -> 管理    
![Shadow](/media/files/2017/02/06/ks_016.png)  
在右侧找到这三个服务  
第一个服务如果不使用SQL PLUS可以不启动  
第二个服务必须启动  
第三个服务必须启动，**OracleServiceXXXX**，XXXX对应的是安装界面上的**全局数据库名**  
![Shadow](/media/files/2017/02/06/ks_017.png)  
右键点击即可选择启动或者关闭服务了  