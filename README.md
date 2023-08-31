
# Installation Steps

## Step 1: Install Apache

Install the Apache web server:
```bash
sudo apt update
sudo apt install apache2
```
Verify that Apache is working:
```bash
sudo systemctl status apache2
```
## Step 2: Install PHP and Modules

Install PHP and required modules:

```bash
sudo apt install libapache2-mod-php8.1 php8.1-mysql php8.1-curl -y
```

Restart Apache to apply changes:


```bash
sudo systemctl restart apache2
```
## Step 3: Test PHP Installation

Create a PHP info file:
```bash
sudo nano /var/www/html/phpinfo.php
```

Add the following content:
```bash
<?php
phpinfo();
?>
```
Access http://localhost/phpinfo.php in your browser. you must see informations about php 

## Step 4: Install MySQL Server and Client
Install MySQL server and client:
```bash
sudo apt install mysql-server mysql-client
```

Restart MySQL:

```bash
sudo systemctl restart mysql
```

## Step 5: Install phpMyAdmin
Install phpMyAdmin:
```bash
sudo apt install phpmyadmin
```
Restart Apache:
```bash
sudo systemctl restart apache2
```

## Step 6: Configure Apache

Edit the Apache configuration file:
```bash
sudo nano /etc/apache2/apache2.conf
```
Add the following line at the end to include phpMyAdmin configuration:
```bash
Include /etc/phpmyadmin/apache.conf
```
Restart Apache:
```bash
sudo systemctl restart apache2
```
## Step 7: Restart MySQL
Restart MySQL to apply changes:
```bash
sudo systemctl restart mysql
```
## Optional : change mysql password 
```bash
sudo mysql -u root -p
```
press enter 

```bash
ALTER USER 'root'@'localhost' IDENTIFIED BY 'new_password'; 
```

## Access phpMyAdmin
Access http://localhost/phpmyadmin in your browser. Log in with your MySQL credentials to start managing your databases.


