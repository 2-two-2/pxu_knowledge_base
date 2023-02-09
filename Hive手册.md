## Hive手册

### Hive启动

```shell
#在node1中进行
#1、启动Hadoop
start-all.sh 
#2、启动metastore服务
nohup /export/server/apache-hive-3.1.2-bin/bin/hive --service metastore &
#3、启动hiveserver2服务
nohup /export/server/apache-hive-3.1.2-bin/bin/hive --service hiveserver2 &
#注意 启动hiveserver2需要一定的时间  不要启动之后立即beeline连接 可能连接不上
# nohup为后台启动  进程挂起  关闭使用jps+ kill -9

#在node3中进行
#4、连接访问
/export/server/apache-hive-3.1.2-bin/bin/beeline

beeline> ! connect jdbc:hive2://node1:10000
beeline> root
beeline> 直接回车
```

### Hive关闭

```shell
#1、退出beeline
Ctrl+D
#2、关闭Hadoop
stop-all.sh

```

### 从Hive中加载数据

```shell
 load data local inpath '/root/hivedata/students.txt' into table itheima.student_local;
```

`将文件放入node1的/root/hivedata/中`







### 基于FineBI的可视化





### 问题归纳

代码没敲完直接回车了，将未敲完的代码，敲完即可。

![image-20221230215457231](C:\Users\zhonghua\AppData\Roaming\Typora\typora-user-images\image-20221230215457231.png)
