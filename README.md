# Readme
A comparison between Indexbase and Database.

### 索引库 vs 数据库
- 索引库常以关系型数据库的形式存在，用途是存储数据索引，格式规整而且大小相对很小，因此能同时保证sync rate和user performance。
- 数据库常以混合型数据库的形式存在，用途是存储数据本体，格式杂乱而且大小相对很大，因此不能同时保证sync rate和user performance。
  - 面向内存数据库通常会为了保证user performance而在一定程度上牺牲sync rate。
  - 面向存储数据库通常会为了保证sync rate而在一定程度上牺牲user performance。

### Credits
- [Oracle Database - Wikipedia](https://en.wikipedia.org/wiki/Oracle_Database)
- [Redis - Wikipedia](https://en.wikipedia.org/wiki/Redis)
- [Apache Cassandra - Wikipedia](https://en.wikipedia.org/wiki/Apache_Cassandra)
