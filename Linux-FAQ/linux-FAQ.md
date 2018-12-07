[TOC]

# 故障库

> linux 故障库

## Ubuntu 故障

1. ubuntu 外放没有声音，耳机有声音。

   > *原因是硬件环境改变之后系统没有自动切换音频设备，此时音频输出依然使用耳机插孔。实际上这是linux的一个缺陷*

   - **解决方法:**

   - **方法一：**

     你在用耳机插一下或者两下插孔他就回切到音响

   - **方法二：**

   > **首选项**-->**声音**,在下面的列表中选**Speakers**，这个是系统音响

2. Ubuntu 登录界面隐藏其他用户登录窗口

   > 当我们创建运行用户时Ubuntu 桌面也会生成登录界面图标，可以创建一个文件来达到隐藏效果。
   >
   > /var/lib/AccountsService/users/"要隐藏的用户"
   > 比如：要隐藏 “www”

   ```shell
   vim /var/lib/AccountsService/users/www
   
   [User]
   SystemAccount=true
   ```

   重启电脑就发现要隐藏的用户不见了。

3. 









## Elasticsearch 故障库

1. **max virtual memory areas vm.max_map_count [65530] likely too low, increase to at least [262144]**

   ```
   echo "vm.max_map_count=262144" >> /tmp/system_sysctl.conf
   sysctl -p
   ```

2. **max number of threads [1024] for user [elasticsearch] is too low, increase to at least [2048]**

   ```
   修改 /etc/security/limits.d/90-nproc.conf 
   
   - soft    nproc     1024
     修改为：
   - soft    nproc     2048
   ```

3. requires kernel 3.5+ with CONFIG_SECCOMP and CONFIG_SECCOMP_FILTER compiled in

   > 使用新的linux版本，内核问题

4. 修改句柄数

   > max file descriptors [4096] for elasticsearch process likely too low, increase to at least [65536]
   > max number of threads [1024] for user [lishang] likely too low, increase to at least [2048]

   ```
   vi /etc/security/limits.conf 
   
   添加如下内容:
   
   * soft nofile 65536
   * hard nofile 131072
   * soft nproc 2048
   * hard nproc 4096
   ```

   扩展：有时正常修改句柄数，不生生效。可以使用一下方法：

   ```
   vim /etc/init/ssh_conf
   
   umask 022 这一行下加入一句：
   
   es  soft  nofile  65536
   ```

5. d

6. 



## CentOS  故障



## kubernets 故障

