# Readme
A comparison between Indexbase and Database.

### Indexbase vs Database

Sync rate和user performance是一对此消彼长的属性。

Bases:
- Indexbase：用途是存储数据索引，其中的每条记录的字节数相对很少，因此Indexbase能同时保证sync rate和user performance。
- Database：用途是存储数据本体，其中的每条记录的字节数一般相对很多，因此Database一般不能同时保证sync rate和user performance。
  - Memory-Oriented Database：要保证user performance。
  - Storage-Oriented Database：要保证sync rate。
    - Document Storage Database：要针对格式支持进行优化。
    - File Storage Database：要针对文件存储进行优化。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
