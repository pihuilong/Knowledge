一、Hive 运行模式

  与 Hadoop 类似，Hive 也有 3 种运行模式：

  1. 内嵌模式

  将元数据保存在本地内嵌的 Derby 数据库中，这是使用 Hive 最简单的方式。但是这种方式缺点也比较明显，因为一个内嵌的 Derby 数据库每次只能访问一个数据文件，这也就意味着它不支持多会话连接。

  2. 本地模式

  这种模式是将元数据保存在本地独立的数据库中（一般是 MySQL），这就可以支持多会话和多用户连接了。

  3. 远程模式

  此模式应用于 Hive 客户端较多的情况。把 MySQL 数据库独立出来，将元数据保存在远端独立的 MySQL 服务中，避免了在每个客户端都安装 MySQL 服务从而造成冗余浪费的情况。
  


二、下载安装 Hive（该步骤已由实验楼完成）

  上节课程我们已经了解到，Hive 是基于 Hadoop 文件系统之上的数据仓库。因此，安装Hive之前必须确保 Hadoop 已经成功安装。本次实验，使用Hive V2.0.0版本。Hive V2.0.0 可以在 Hadoop V2.4.x 以上环境中工作。

  下载apache-hive-2.0.0-bin.tar.gz 后，对其进行解压：

  tar zxvf apache-hive-2.0.0-bin.tar.gz

  也可以在/opt目录中找到解压好的包。
  

三、配置系统环境变量（该步骤已由实验楼完成）

  修改/etc/profile文件，这个我们在 Hadoop 和 HBase 的课程 中也修改过，应该比较熟悉了。  
    sudo vim /home/hadoop/.bashrc
    # Hive environment
    export HIVE_HOME=/opt/apache-hive-2.0.0-bin
    export PATH=$PATH:$HIVE_HOME/bin
    
    
四、内嵌模式

1）hive-site.xml

$HIVE_HOME/conf 对应的是 Hive 的配置文件路径，类似于之前学习的HBase, 该路径下的 hive-site.xml 是 Hive 工程的配置文件。默认情况下，该文件并不存在，我们需要拷贝它的模版来实现（这里暂时不需要修改，先拷贝）：

$ sudo cp hive-default.xml.template hive-site.xml
hive-site.xml 的主要配置有一下，不需要修改：

此处输入图片的描述

此处输入图片的描述

hive.metastore.warehouse.dir

该参数指定了 Hive 的数据存储目录，默认位置在 HDFS 上面的 /user/hive/warehouse 路径下。
hive.exec.scratchdir

该参数指定了 Hive 的数据临时文件目录，默认位置为 HDFS 上面的 /tmp/hive 路径下。
