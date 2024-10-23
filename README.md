# Readme
A note about Sync Rate.

### Sync Rate

存储一致性是指数据在内存和外存之间的一致程度。存储一致性关于Sync Rate的函数的特点是：Sync Rate越小，存储一致性越小，Sync Rate越大，存储一致性越大。

问题：许多场景要求必须保证存储一致性，所以必须设置很高的Sync Rate，但是随着数据量的增大，响应及时性会逐渐降低直至丧失。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
