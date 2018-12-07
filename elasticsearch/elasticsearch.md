# Elasticsearch

* Elasticsearch 写入步骤详解 

> **步骤1：**新document首先写入内存Buffer缓存中。
>
> **步骤2：**每隔一段时间，执行“commitpoint”操作，buffer 写入新Segment中。
>
> **步骤3：**新segment写入文件系统缓存 filesystem cache。
>
> **步骤4：**文件系统缓存中 index segment 被fsync 强制刷到磁盘上，确保物理写入。此时，新segment 被打开供search 操作。
>
> **步骤5：**清空内存buffer,可以接受新的文档写入。

官方解读地址：<http://t.cn/EyhPQt5>

这是传统意义的写入步骤，实际 ES 为保证`实时性`，会做 refresh 操作。

* jdk 安装

  > export JAVA_HOME=/mobboy/app/jdk/
  > export PATH=$JAVA_HOME/bin:$PATH




