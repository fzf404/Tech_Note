<!-- 
title: WSL2
sort: 
--> 
# WSL2

### 开启WSL2

> WSL2[升级](https://docs.microsoft.com/zh-cn/windows/wsl/install-win10)
>
> 彩蛋：`wslfetch`

```powershell
# 切换至wsl2
wsl --set-version debian 2	
# m
\\wsl$
```



## mysql

### 问题

- 2013 - Lost connection to MySQL server

  > `cd /etc/mysql/mysql.conf.d`
  >
  > `sudo vi mysqld.cnf`
  >
  > 找到【mysqld】模块
  >
  > 增加一行：`skip-name-resolve` 
  >
  > 并重启mysql服务：`service mysql restart `

- 1130 - Host 127.0.0.1 is not allowed to connect to this MySQL server

  > ```bash
  > mysql -u root -p
  > 
  > use mysql;
  > select host from user where user='root';# 配置信息
  > update user set host = '%' where user ='root';	# 设置允许登录的IP
  > flush privileges;	# 立即生效
  > ```