## Oracle内存结构图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210314123222349.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzNDUzNzg0,size_16,color_FFFFFF,t_70#pic_center)
## System Global Aera （SGA）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210314123331312.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzNDUzNzg0,size_16,color_FFFFFF,t_70#pic_center)

		V$SGASTAT视图提供有关SGA更详细的内存分配信息。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021031412342827.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzNDUzNzg0,size_16,color_FFFFFF,t_70#pic_center)

	V$SGA视图给出了系统全局区(System Global Area，SGA)内存结构的摘要信息。
### 数据库缓存区（Database Buffer Cache）
&emsp;&emsp;用于缓存当前或最近使用的从磁盘读取的数据块的拷贝，来优化数据库的I/O减少物理读/写。Oralce依据LRU算法对该内存区域进行block-level的更新。数据高速缓存块又由以下几个缓存块组成：
**※ 脏缓存块（Dirty buffers）**
  保存被修改过并且commit但未写入磁盘数据的缓存块，脏缓存块最终被DBWn进程写入到硬盘的数据文件中永久保存。
**※ 命中缓存块（Pinned buffers）**
  保存最近正在被访问的缓存块，始终被保留在数据高速缓存中，不会被写入数据文件。
**※ 空闲缓存块（Free buffers）**
  该缓存块中没有数据，等待被写入数据。oracle从数据文件中读取数据后，寻找空闲缓存块，以便写入其中。
### 日志缓冲区（Redo Log Buffer）
&emsp;&emsp;日志缓冲区是一块比较小的内存区域，它是用来短期存储将写入到磁盘中的重做日志信息。日志缓冲区也是为了减少磁盘IO，减少用户的等待时间。
### 共享池（Shared Pool）
- 数据字典缓存区（Data Dictionary Cache）
用于存放SQL语句相关的数据文件、表、索引、列、用户、其他的数据对象的定义和权限信息等。

- 库缓存区（Librabry Cache）
共享SQL和PL/SQL代码。服务器进程在执行语句时，首先会匹配库缓存，如果存在相同语句则无需编译直接使用已编译的执行计划。
绑定变量不是在编译阶段赋值的，而是在运行阶段赋值的，因此含有绑定变量的SQL语句可以不用重新编译。

- SQL和PL/SQL结果缓存（Server Result Cache）
用于存储SQL查询或PL/SQL函数的结果，以加快其将来的执行速度。
### 大池（Large Pool）
&emsp;&emsp;大池是个可选的内存区域，可提供一个大的缓冲区供数据库的备份与恢复操作过程使用。数据库的备份恢复、执行具有大量排序操作的SQL语句、并行化的数据库操作时可能需要用到大池。
### Java池（Java Pool）
&emsp;&emsp;JAVA池在数据库中支持JAVA 的运行，存放JAVA代码和JAVA语句的语法分析表。
### 流池（Stream Pool）
&emsp;&emsp;用于缓存流进程在数据库间移动/复制数据时使用的队列消息。一般从重做日志中提取变更记录的进程和应用变更记录的进程会用到流池。
## Program Global Aera （PGA）
&emsp;&emsp;PGA是指单个服务器进程或者单个后台进程所需的数据和控制信息。PGA是在用户进程连接到数据库并创建一个会话时自动分配。该区域内保留每个与oracle数据库连接的用户进程所需的内存，当一个用户会话结束，PAG就会释放。

1. Private SQL area：包含绑定信息、运行时的内存结构。每个发出sql语句的会话，都有一个private SQL area（私有SQL区）
	**专有服务器连接私有SQL区在PGA中，共享服务器连接私有SQL区在SGA中。**
2. Session memory：为保存会话中的变量以及其他与会话相关的信息，而分配的内存区。

**※ 排序区**
  当用户需要对数据进行排序时，系统会将需要排序的数据保存到PGA中的排序区内，然后在这个排序区内对这些数据进行排序。如果发现用户的很多操作都需要用到排序，那么为用户设置比较大的排序区，可以提高用户访问数据的效率。
**※ 会话区**
  会话区保存了会话所具有的权限、角色、性能统计等信息，通常都是由数据库系统自我维护。
**※ 堆栈区**
  保存着绑定变量、会话变量、SQL语句运行时的内存结构等重要的信息，通常都是由数据库系统自我维护
**※ 游标区**
  游标区是一个动态的区域，当用户执行游标语句打开游标时，系统会在PGA中创建游标区，当关闭游标时，这个区域就会被释放。创建与释放需要占用一定的系统资源，花费一定的时间，如果频繁的打开和关闭游标，就会降低语句的执行性能。
## User Global Aera （UGA）
&emsp;&emsp;为用户进程存储会话状态。UGA可以作为SGA或者PGA的一部分，如果通过一个共享服务器连接，UGA包含在SAG中；如果通过一个专有服务器连接，UGA就包含在专有服务器的PGA中。
## Software code areas
&emsp;&emsp;Oracle存放自身软件代码的一部分内存区，不允许其他会话访问。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210314124641806.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzNDUzNzg0,size_16,color_FFFFFF,t_70#pic_center)
