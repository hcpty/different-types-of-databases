# Readme
A note about Sync Rate and User Performance.

### Sync Rate and User Performance

##### Sync Rate and User Performance

Sync rate和user performance是一对此消彼长的属性，因为虽然磁盘缓冲和内核磁盘缓冲之间的数据拷贝通常通过Direct Memory Access Transfer的方式进行，不需要CPU全程控制，但是用户程序缓冲和内核磁盘缓冲之间的数据拷贝通常通过Traditional Memory Access Transfer的方式进行，需要CPU全程控制，而且，要传送的字节数越多，要占用的CPU循环就越多。

考虑以下4种场景：
- 数据量小，而且选择了sync rate first的解决方案，那么user performance是容易保证的。
- 数据量小，而且选择了user performance first的解决方案，那么sync rate是容易保证的。
- 数据量大，而且选择了sync rate first的解决方案，那么user performance是不容易保证的。
- 数据量大，而且选择了user performance first的解决方案，那么sync rate是不容易保证的。

这意味着：
- 当数据量小的时候，容易兼顾sync rate和user performance。
- 当数据量大的时候，不容易兼顾sync rate和user performance，必须在sync rate和user performance之间进行适当的取舍。

##### 索引存储 vs 内容存储

对内容建立索引的目的是加快查找。索引和内容有如下区别：
- 一般情况下，索引的数据量相对很小。
- 一般情况下，内容的数据量相对很大。

此时，如果选择了sync rate first的解决方案，将会严重影响索引上的user performance，这就违背了索引的初衷，针对这种场景的最佳实践是将内容和索引分开存储。当然，如果选择了user performance first的解决方案，则一般影响不会很大。

##### 索引数据库 vs 内容数据库

关系型数据库支持复杂的索引，支持显式的锁，所以是存储索引的优良场所，关系型数据库的主要用途之一就是存储索引。关系型数据库不适合存储内容的原因包括：
- 对内容格式的支持有限，一般只限于表，因为关系型数据库正是由此得名。
- 对数据量的支持有限，因为关系型数据库一般都是sync rate first的。

NoSQL支持丰富的内容格式，支持大数据量，所以是存储内容的优良场所，NoSQL的主要用途之一就是存储内容。NoSQL适合存储内容的原因包括：
- 针对内容格式进行了优化，例如针对JSON内置序列化和反序列化，针对二进制文件存储进行了优化。
- 针对数据量的支持进行了优化，允许在一定程度上牺牲sync rate以保证大数据量下的user performance。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
