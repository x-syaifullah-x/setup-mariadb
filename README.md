# SETUP DATABASE MARIADB

### INSATLL MARIADB-SERVER
```bash
sudo apt install --no-install-suggests --no-install-recommends mariadb-server
```

### RESTART MARIADB SOCKET
```bash
sudo systemctl restart mariadb.socket
```

### RESTART MARIADB SERVICE
```bash
sudo systemctl restart mariadb.service
```

### UPDATE /etc/mysql/conf.d/mysql.cnf (if mariadb.service not running)
```bash
sudo editor /etc/mysql/conf.d/mysql.cnf
```
```
[mysqld]
user		= mysql
pid-file	= /var/run/mysqld/mysqld.pid
socket		= /var/run/mysqld/mysqld.sock
port		= 3306
datadir		= /var/lib/mysql
```

- **Restart Mariadb Socket**

    ```bash
    sudo systemctl restart mariadb.socket
    ```

- **Restart Mariadb Service**

    ```bash
    sudo systemctl restart mariadb.socket
    ```

### OPEN MARIADB
```bash
sudo maridb
```
- **Setup Password**
    ```sql
    ALTER USER 'root'@'localhost' IDENTIFIED BY '123456789';
    flush privileges;
    exit;
    ```

- **Login**
    ```bash
    maridb -u $user_name -p $password
    ```
