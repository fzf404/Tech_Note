<!-- 
title: MongoDB
sort: 
--> 

[官方图形化工具](https://www.mongodb.com/try/download/compass)

## 安装

```bash
sudo apt install mongodb
# 远程连接修改配置文件
vim /etc/mongodb.conf
ip: 127.0.0.1 -> 0.0.0.0 
systemctl restart mongodb
```

## 操作

```bash
# 连接
mongo "mongodb+srv://cluster0.11tv4.gcp.mongodb.net/myFirstDatabase" --username fzf404 

# 导入数据
mongoimport --uri="mongodb+srv://fzf404:<password>@cluster0.11tv4.gcp.mongodb.net/test"  -c product products.json

# 设置密码
use admin
db.createUser({user: 'root', pwd: '123456', roles: ['root']})
db.auth('root', '123456')	# 验证成功

vim /etc/mongodb.conf
auth: true
systemctl restart mongodb
```

