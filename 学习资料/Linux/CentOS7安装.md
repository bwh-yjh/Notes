# CentOS 7虚拟机安装后

## 一、新建虚拟机

![image-20220410003255587](CentOS7安装.assets/image-20220410003255587.png)

### 1、选择典型

![image-20220410003358868](CentOS7安装.assets/image-20220410003358868.png)

### 2、选择CentOS镜像

![image-20220410003518281](CentOS7安装.assets/image-20220410003518281.png)

### 3、选择存储位置

![image-20220410003636484](CentOS7安装.assets/image-20220410003636484.png)

### 4、虚拟机磁盘配置

![image-20220410003707563](CentOS7安装.assets/image-20220410003707563.png)

### 5、自定义其他配置

![image-20220410004443694](CentOS7安装.assets/image-20220410004443694.png)

## 二、系统安装

### 1、虚拟机配置完成之后进入系统安装界面

![image-20220410005009362](CentOS7安装.assets/image-20220410005009362.png)

出现此界面后敲“回车”进入安装程序

### 2、选择安装语言

![image-20220410005118700](CentOS7安装.assets/image-20220410005118700.png)

### 3、分区选择

虽然默认会自动帮我们格式化磁盘，但也需要点击确认一下

![image-20220410005159935](CentOS7安装.assets/image-20220410005159935.png)

点击左上角完成即可

![image-20220410005222117](CentOS7安装.assets/image-20220410005222117.png)

### 4、开始安装

![image-20220410005239592](CentOS7安装.assets/image-20220410005239592.png)

安装过程中我们可以设置密码

![image-20220410005308917](CentOS7安装.assets/image-20220410005308917.png)

### 5、安装完成

 当出现“重启”按钮时，说明系统已经安装完成

![image-20220410005332882](CentOS7安装.assets/image-20220410005332882.png)

重启后的样子

![image-20220410005346598](CentOS7安装.assets/image-20220410005346598.png)

至此，我们在VMware中对CentOS的基本安装已经完成

## 三、Linux配置

配置上网

- 修改配置网卡配置文件

```shell
vi /etc/sysconfig/network-scripts/ifcfg-ens33	
```

![image-20220410011540666](CentOS7安装.assets/image-20220410011540666.png)

- 修改 `ONBOOT=yes`

- 重启网络服务

```shell
systemctl restart network
```

至此，我们的虚拟机就可以访问互联网了。