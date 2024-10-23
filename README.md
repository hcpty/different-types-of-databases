# Readme
A note about different types of databases.

### 不同类型的数据库

##### 严格要求存储一致性的数据库

存储一致性是指数据在内部主存和外部存储之间的一致程度。

存储一致性关于Sync Rate的函数的特点是：Sync Rate越小，存储一致性越小，Sync Rate越大，存储一致性越大。

许多场景对存储一致性有严格的要求，因此需要把Sync Rate设置成一个很大的值。

在这类数据库中，CPU会花费较多的时间用于在数据库缓冲和内核磁盘缓冲之间拷贝数据。

##### 严格要求响应及时性的数据库

响应及时性是指数据库响应每一个查询请求的速度。

响应及时性关于Sync Rate的函数的特点是：Sync Rate越小，响应及时性越大，Sync Rate越大，响应及时性越小。

许多场景对响应及时性有严格的要求，因此需要把Sync Rate设置成一个很小的值。

在这类数据库中，CPU会花费较多的时间用于在数据库缓冲和内核网卡缓冲之间拷贝数据。

##### 模式数据库
为了保证查找速度，通常使用内部对齐的方式存储数据。主要用于存储表中的行，行是具有严格约束的结构。

##### 结构数据库或结构存储
可能使用内部对齐的方式存储数据，也可能使用内部链接的方式存储数据。主要用于存储各种有结构的数据，对数据的结构没有严格的约束。

##### 文件数据库或文件存储
为了支持变长存储，通常使用内部链接的方式存储数据。主要用于存储二进制文件。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
- [DB-Engines - Knowledge Base of Relational and NoSQL Database Management Systems](https://db-engines.com/)
