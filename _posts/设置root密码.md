---
layout: post
title: "谷歌云设置root密码及开启ssh权限"
tags: [GCP,VPS,GOOGLE]
comments: true
---

##  设置root密码

### 1.先选择从浏览器打开ssh连接服务器

![img](https://www.v2rayssr.com/wp-content/uploads/2019/12/v2rayssr.com163247.png)

### 2.切换到root账号，输入代码

```
sudo -i
```

### 3.设置root密码

```
passwd
```

然后会要求输入新密码，然后再重复一次密码，输入密码的时候不会显示出来，所以直接输入密码，然后回车，再然后重复输入密码回车

![img](https://www.v2rayssr.com/wp-content/uploads/2019/12/v2rayssr.com163251.png)

## 开启SSH权限

CentOS和Debian通用，输入以下两条命令

```
sed -i 's/PermitRootLogin no/PermitRootLogin yes/g' /etc/ssh/sshd_config
sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
```

Ubuntu系统，输入以下两条命令

```
sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config
sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
```

重启服务器

```
reboot
```

