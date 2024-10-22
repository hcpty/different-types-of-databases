# Readme
A comparison between Indexbase and Database.

### Indexbase vs Database
- Indexbase的用途是存储数据索引，其中的每条记录的字节数都相对很少，因此Indexbase能同时保证sync rate和user performance。
- Database的用途是存储数据本体，其中的每条记录的字节数都相对很多，因此Database不能同时保证sync rate和user performance。
  - 面向memory的Database通常会为了保证user performance而在一定程度上牺牲sync rate。
  - 面向storage的Database通常会为了保证sync rate而在一定程度上牺牲user performance。

### Credits
- [Oracle Database - Wikipedia](https://en.wikipedia.org/wiki/Oracle_Database)
- [Redis - Wikipedia](https://en.wikipedia.org/wiki/Redis)
- [Apache Cassandra - Wikipedia](https://en.wikipedia.org/wiki/Apache_Cassandra)
