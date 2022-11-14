## Install **Apache 2**
```
sudo apt update && sudo apt install apache2
```
- Managing Apache 
    ```
    sudo systemctl status apache2
    sudo systemctl stop apache2
    sudo systemctl start apache2
    sudo systemctl restart apache2
    sudo systemctl reload apache2
    sudo systemctl disable apache2
    sudo systemctl enable apache2
    ```
- Konfigurasi Firewall 
    ```
    sudo ufw app list
    sudo ufw allow 'Apache Full
    sudo ufw status
    ```
- Install PHP
    ```
    sudo apt install -y php libapache2-mod-php
    ```
- if you want to do a costum domain you can check on google

## Install **Mysql Server**

```
sudo apt install mysql-server
```
- Managing Mysql-server 
    ```
    sudo systemctl start mysql.service
    ```
- Configure Mysql-server 
    ```
    sudo mysql_secure_installation
    ```
- Manage User Database 
    ```
    sudo mysql

    ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
    ```
    ```
    mysql -u root -p

    ALTER USER 'root'@'localhost' IDENTIFIED WITH auth_socket;
    ```
    ```
    sudo mysql_secure_installation
    ```
- Determine the strength of the password
    ```
    SHOW VARIABLES LIKE 'validate_password%';

    SET GLOBAL validate_password.policy = 0;   // For LOW 
    SET GLOBAL validate_password.policy = 1;   // For MEDIUM 
    SET GLOBAL validate_password.policy = 2;   // For HIGH 
    ```
- Create new user
    ```
    SELECT user, host FROM mysql.user;  // Show User
    drop user name_user@localhost;      // Delete User

    create user 'username'@'localhost' identified by 'password';
    GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;
    FLUSH PRIVILEGES; 
    ```
- If you want to login with new user then use
    ```
    mysql -u username -p
    ```

## Install **Phpmyadmin + Module PHP**
```
sudo apt install -y phpmyadmin php-mbstring php-zip php-gd php-json php-curl libapache2-mod-php php-mysqlnd php-xml
```

