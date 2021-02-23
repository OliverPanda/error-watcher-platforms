### 安装步骤
主要奥步骤分为: 
-  下载源码包  
-> 解压源码包到指定目录(/usr/lib/mysql)  
-> 添加mysql用户组, 添加mysql用户到mysql用户组, 把/usr/local/mysql的所有者设为mysql
-> **切换为mysql用户**
-> 创建data目录(/usr/lib/mysql/data/mysql)
-> 初始化mysql

1. 下载源码

2. 



问题：
- 切换为mysql用户`su mysql`的时候, 报错`This account is currently not available`
vi /etc/passwd查看帐号信息； 发现mysql的shell是`/sbin/nologin` 改成`/bin/bash`

- 