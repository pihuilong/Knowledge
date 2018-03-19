## 常用Linux命令
* top   : 查看系统资源使用情况
* ps -aux | sort -k4nr | head -n 10     ： 查看内存占用前10的进程
* echo 3 > /proc/sys/vm/drop_caches     ： 清空 buff/cache
* yum -y remove tigervnc-server         ： 删除程序 tigervnc-server (for example)
* kill 1697                             ： 杀掉pid为1697的进程，使用 kill -9 pid 可以强制杀掉
* rpm -e gdm-1:3.22.3-13.el7_4.x86_64   ： 卸载程序，若有其他程序依赖，则无法卸载，需要加参数--nodeps忽略（不推荐，可使用yum -y remove）
* systemctl restart mysqld              ： 重启服务 mysqld (for example)
* systemctl status mysqld               ： 查看服务状态   mysqld
* systemctl enable mysqld               ： 设置服务开机自启动  mysqld
*


### 找到软件的安装路径方法
> 对于通过yum或者rpm方式安装的：
* rpm -qa shadow*    ： 查找到包含shadow的软件的准确名字，如shadowsocks-qt5-2.9.0-2.el7.centos.x86_64
* rpm -ql shadowsocks-qt5-2.9.0-2.el7.centos.x86_64     ： 查看与该软件有关的所有路径

> 对于通过源码安装的
* ps -aux | grep *            ： 找出对一个的可执行文件所在的目录
* 通常安装完包后，我们都会把他加入到服务里面，你可以去/etc/rc.d/下找相应的文件，进而确认相关信息。

> 最后一种最笨的方法就是用find命令 find / -name *文件名*
