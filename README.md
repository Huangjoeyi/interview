* [PHP](#php)
* [MySQL](#mysql)
* [Redis](#redis)
* [Linux](#linux)
* [Nginx](#nginx)
* [算法](#算法)
* [系统设计](#系统设计)

##### PHP

一，使用过的各个框架的优缺点。

二，PHP类自动加载原理。

三，Laravel源码相关。比如容器是如何实现的？

四，Composer是如何实现自动加载的？

五，PHP数组的底层实现。自己如何去实现？

六，一个请求到PHP，Nginx的主要过程。完整描述整个网络请求过程，原理。

七，fpm的配置，动/静态，参数相关。

八，php多进程如何实现？

九，PHP的魔术方法。

```php
__set() // 在给不可访问属性赋值时，__set()会被调用
__get() // 读取不可访问属性的值时，__get()会被调用
__isset() //当对不可访问属性调用isset()或empty()，__isset()会被调用
__unset() // 当对不可访问属性调用unset()时，__unset()会被调用
__call() // 在对象中调用一个不可访问方法时，__call()会被调用
__callStatic() // 在静态上下文中调用一个不可访问的方法时，__callStatic会被调用
__construct() // 构造函数的类会在每次创建新对象时先调用此方法，所以非常适合在使用对象之前做一些初始化工作。
__destruct() // 析构函数会在到某个对象的所有引用都被删除或者当对象被显式销毁时执行。
__sleep() // serialize()函数会检查类中是否存在一个魔术方法__sleep()，如果存在，该方法会先被调用，然后再执行序列化操作。此功能可以用于清理对象，并返回一个包含对象中所有应被序列化的变量名称的数组。如果该方法未返回任何内容，则 NULL 被序列化，并产生一个 E_NOTICE 级别的错误。
__wakeup() // unserialize()函数会检查是否存在一个__wakeup()方法，如果存在，则会先调用该方法，然后再执行反序列化操作。__wakeup() 经常用在反序列化操作中，例如重新建立数据库连接，或执行其它初始化操作。
```

#### MySQL

一，MySQL底层的数据结构是什么？最左前缀的原理。

二，使用索引时需要注意的点有哪些？

三，MySQL底层原理：为什么select*有问题？大字段索引有问题？

四，有过哪些优化MySQL的经验？

五，数据量大的表分页偏移值越大为什么查询越慢？跟底层原理有关。

六，MySQL主从同步延迟如何处理？

#### Redis

一，Redis五大数据类型对应的底层数据结构是什么？

#### Linux

一，分析access.log日志中前100的url。

二，Linux的I/O多路复用。

三，进程，线程，协程是什么？如何切换的？

#### Nginx

一，Nginx性能优化；openresty相关等。

二，PHP请求是如何到Nginx服务器的。

三，服务器负载均衡的实现。

#### 算法

一，找出数组中出现一次的元素。10 10 11 11 12 13 12 13 16 只出现一次的数字。要求时间复杂度尽可能低。

二，消消乐816。如下:

1）字符818166816消除816后为空。

2）字符81816816816消除后是81.

三，最小公共子串。

四，各种排序算法。

- 快速排序。[源码](./src/ algorithms/quickSort.php)

  > 最坏情况出现在每次切分所选的切分元素总是当前切分数组的最小值时，因为其在排序过程中，会交换元素打乱数组原本的相对顺序，所以快速排序是不稳定的算法。
  >
  > 最坏时间复杂度：O(n^2)，平均时间复杂度：O(n*log2n)。

- 冒泡排序。[源码](./src/ algorithms/bubbleSort.php)

  > 时间复杂度：O(n^2)。

五，Excel给定一个数据，如何查到它在第几列？(excel头部有规律：A | B | C | D | E | …… | Z | AA | AB | AC | AD | AE | …… | AZ | ……)

六，打印目录结构。[源码](./src/ algorithms/loopDir.php)

#### 系统设计

一，短链接如何设计？

二，接口访问限制。每30分钟只能访问100次/每30分钟只能访问100次，两种情况。

三，LRU如何实现？

四，订单表订单ID如何设计生成？