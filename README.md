# Readme
A comparison between Indexbase and Database.

### Indexbase vs Database

Sync rate和user performance是一对此消彼长的属性，因为虽然磁盘缓冲和内核磁盘缓冲之间的数据拷贝通常通过Direct Memory Access Transfer的方式进行，不需要CPU全程控制，但是用户程序缓冲和内核磁盘缓冲之间的数据拷贝必须通过Traditional Memory Access Transfer的方式进行，需要CPU全程控制，而且传送的数据的字节数越多，占用的CPU循环就越多。

Bases:
- Indexbase：存储数据索引，其中每条记录的字节数一般相对很少，因此Indexbase能同时保证sync rate和user performance。
- Database：存储数据本体，其中每条记录的字节数一般相对很多，因此Database不能同时保证sync rate和user performance。
  - Memory-Oriented Database：针对user performance进行了优化。
  - Storage-Oriented Database：针对sync rate进行了优化。
    - Document Storage Database：针对格式支持进行了优化。
    - File Storage Database：针对文件存储进行了优化。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
