[\[back\]](../)

# Installation of MySql 5.7

[1]. Installing MySQL repo from dev.mysql.com

```bash
sudo dnf localinstall \
https://dev.mysql.com/get/mysql57-community-release-el7-11.noarch.rpm
```

[2]. Installing MySql 5.7

```bash
sudo dnf install \
mysql-community-server \
mysql-community-client \
mysql-community-common \
mysql-community-libs \
mysql-community-libs-compat
```

[3]. Start MySQL 

```bash
# Start mysqld 
sudo systemctl start mysqld

# Enable mysqld
sudo systemctl enable mysqld

# Check status
sudo systemctl status mysqld
```

[4]. Grab the temporary password

```bash
sudo grep 'temporary password' /var/log/mysqld.log
```
Take note of the temporary password for the securing installation
process later.

```bash
### Output
2020-07-31T10:33:33.257274Z 1 [Note] A temporary password is generated
for root@localhost: 
```

[5]. Run the `mysql_secure_installation`

```bash
mysql_secure_installation
```

[6]. Check the version

```bash
~ mysql -uroot -p
Enter password:

mysql> select @@VERSION;
+-----------+
| @@VERSION |
+-----------+
| 5.7.31    |
+-----------+
1 row in set (0.00 sec)
```

