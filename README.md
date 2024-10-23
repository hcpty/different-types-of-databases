# Readme
A note about different types of databases.

### 不同类型的数据库

##### 严格要求存储一致性的数据库

存储一致性是指数据在内存和外存之间的一致程度。

存储一致性关于Sync Rate的函数的特点是：Sync Rate越小，存储一致性越小，Sync Rate越大，存储一致性越大。

许多场景对存储一致性有严格的要求，因此需要把Sync Rate设置成一个很大的值。

在Sync Rate的值很大的情况下，随着数据量的逐渐增大，CPU会花费越来越多的时间用于在数据库缓冲和内核磁盘缓冲之间拷贝数据。

##### 严格要求响应及时性的数据库

许多场景对响应及时性有严格的要求，因此需要把Sync Rate设置成一个很小的值。

随着数据量的逐渐增大，CPU会花费越来越多的时间用于在数据库缓冲和内核网卡缓冲之间拷贝数据。

##### 模式数据库

##### 文档数据库

##### 文件数据库

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
- [DB-Engines - Knowledge Base of Relational and NoSQL Database Management Systems](https://db-engines.com/)
