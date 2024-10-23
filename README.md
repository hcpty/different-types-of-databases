# Readme
A note about Sync Rate and User Performance.

### Sync Rate and User Performance

Sync rate和user performance是一对此消彼长的属性，因为虽然磁盘缓冲和内核磁盘缓冲之间的数据拷贝通常通过Direct Memory Access Transfer的方式进行，不需要CPU全程控制，但是用户程序缓冲和内核磁盘缓冲之间的数据拷贝必须通过Traditional Memory Access Transfer的方式进行，需要CPU全程控制，而且，要传送的字节数越多，要占用的CPU循环就越多。

考虑以下4种场景：
- 数据量小，而且选择了sync rate first的解决方案，那么user performance是很容易保证的。
- 数据量小，而且选择了user performance first的解决方案，那么sync rate是很容易保证的。
- 数据量大，而且选择了sync rate first的解决方案，那么user performance是不容易保证的。
- 数据量大，而且选择了user performance first的解决方案，那么sync rate是不容易保证的。
这意味着当数据量小的时候，容易兼顾sync rate和user performance，而当数据量大的时候，则必须在sync rate或user performance之间进行适当的取舍。

经常对内容建立索引，以加快查找，内容和索引有如下区别：
- 一般情况下，内容的数据量相对很大。
- 一般情况下，索引的数据量相对很小。
此时，如果选择了sync rate first的解决方案，将会严重影响索引上的user performance，这违背了索引的初衷，针对这种场景的最佳实践是将内容和索引分开存储。

### Credits
- Computer Systems: A Programmer's Perspective, Third Edition
