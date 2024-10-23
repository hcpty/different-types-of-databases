# Readme
A note about Sync Rate.

### Sync Rate

存储一致性是指数据在内存和外存之间的一致程度。

存储一致性关于Sync Rate的函数的特点是：Sync Rate越小，存储一致性越小，Sync Rate越大，存储一致性越大。

许多场景对存储一致性有强制要求，所以必须把Sync Rate设置为某个很大的值，但是在Sync Rate的值很大的情况下，随着数据量的增大，响应及时性会逐渐降低直至丧失。为解决这种问题，可以对数据进行分区存储。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
