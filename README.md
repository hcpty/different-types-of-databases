# Readme
A note about different types of databases.

### 不同类型的数据库

第一种分类依据是sync rate。第二种分类依据是data structure。

##### 高一致性数据库
- 存储一致性是指数据在内存和外存之间的一致程度。存储一致性关于sync rate的函数的特点是：sync rate越小，存储一致性越小，sync rate越大，存储一致性越大。许多场景对存储一致性有非常严苛的要求，因此需要把sync rate设置成一个很大的值。
- 在这类数据库中，CPU会花费较多的时间用于在数据库缓冲和内核磁盘缓冲之间拷贝数据。

##### 高及时性数据库
- 响应及时性是指数据库响应每一个查询请求的速度。响应及时性关于sync rate的函数的特点是：sync rate越小，响应及时性越大，sync rate越大，响应及时性越小。许多场景对响应及时性有非常严苛的要求，因此需要把sync rate设置成一个很小的值。
- 在这类数据库中，CPU会花费较多的时间用于在数据库缓冲和内核网卡缓冲之间拷贝数据。

##### 通用数据库
- 可以存储各种数据，例如JSON、BitArray、List、Set、String等。
- 根据要存储的数据的统计长度，可能使用内部对齐的方式存储数据，也可能使用内部链接的方式存储数据。

##### 模式数据库
- 专门存储有模式约束的数据，模式是指对数据的结构、字段的类型和大小施加的约束。
- 因为数据的结构、字段的类型和大小都是确定的，所以可以使用内部对齐的方式存储数据。

##### 文件数据库
- 专门存储二进制文件，例如图片、视频、Excel文件、程序安装包、压缩包等。
- 通常使用内部链接的方式存储数据，以支持存储可变长度的文件。

### Credits
- [DB-Engines - Knowledge Base of Relational and NoSQL Database Management Systems](https://db-engines.com/)
