#### Mysql 允许其他电脑连接我的数据库

```sql
命令行：
mysql -u root -p

输入密码：
****

use mysql

select user, host from user;
查看该user下的root的host是不是localhost如果是：
update user set host = '%' where user='root';

赋予权限
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'password' WITH GRANT OPTION;

立即执行
flush privileges

```

打开mysql work bench hostname修改为当前主机的IP地址。

其他的电脑就可以连接到我的数据库了。