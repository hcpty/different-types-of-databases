# Readme
A comparison between Indexbase and Database.

### Indexbase vs Database
- Indexbase的用途是存储数据索引，其中的每条记录的字节数相对很少，因此Indexbase能同时保证sync rate和user performance。
- Database的用途是存储数据本体，其中的每条记录的字节数一般相对很多，因此Database一般不能同时保证sync rate和user performance。
  - Memory-Oriented Database通常会为了保证user performance而牺牲一部分sync rate。
  - Storage-Oriented Database通常会为了保证sync rate而牺牲一部分user performance。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
