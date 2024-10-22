# Readme
A comparison between Indexbase and Database.

### 索引库 vs 数据库
- 索引库的用途是存储数据索引，其中的每条记录的字节数都相对很少，因此索引库能同时保证sync rate和user performance。
- 数据库的用途是存储数据本体，其中的每条记录的字节数都相对很多，因此数据库不能同时保证sync rate和user performance。
  - 面向memory的数据库通常会为了保证user performance而在一定程度上牺牲sync rate。
  - 面向storage的数据库通常会为了保证sync rate而在一定程度上牺牲user performance。

### Credits
- [Oracle Database - Wikipedia](https://en.wikipedia.org/wiki/Oracle_Database)
- [Redis - Wikipedia](https://en.wikipedia.org/wiki/Redis)
- [Apache Cassandra - Wikipedia](https://en.wikipedia.org/wiki/Apache_Cassandra)
