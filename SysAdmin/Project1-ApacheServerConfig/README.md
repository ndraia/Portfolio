# LAMP Stack Web Server Setup on Linux Distributions

## Introduction
This project provides instructions for installing and configuring a LAMP (Linux, Apache, MySQL/MariaDB, PHP) stack on three major Linux distribution families: Debian/Ubuntu, Red Hat/CentOS, and Arch Linux. Each section will guide you through the specific steps required for your chosen distribution. 

## 1. Prerequisites
   
- A Linux distribution (e.g., Ubuntu, Debian, CentOS, ArchLinux)
- Basic knowledge of Linux command line
- Access to a terminal with root privileges

## 2. Installation Steps
   
## Install Linux
Begin by installing a Linux distribution of your choice. You can use a virtual machine or install it directly on your system.

## 3.1 Debian/Ubuntu

#### 1. Update the System

```bash
sudo apt update && sudo apt upgrade
```
#### 2. Install Apache
Update the package index and install Apache

```bash
sudo apt install apache2 sudo systemctl start apache2 sudo systemctl enable apache2
```

#### 3. Install MySQL/MariaDB

```bash
sudo apt install mysql-server sudo mysql_secure_installation
```

#### 4. Install PHP

```bash
sudo apt install php lbapache2-mod-php php-mysql sudo systemctl restart apache2
```

#### 5. Verify the Setup

```bash
sudo nano /var/www/html/info.php
```

Add the following content:

```php
<?php
phpinfo();
?>
```
Visit http://your-server-ip/info.php to verify.

#### 6. Clean Up

```bash
sudo rm /var/www/html/info.php
```

## 3.2 Red Hat/CentOS

#### 1. Update the System

```bash
sudo yum update
```

#### 2. Install Apache

```bash
sudo yum install httpd sudo systemctl start httpd sudo systemctl enable httpd
```

#### 3. Install MySQL/MariaDB

```bash
sudo yum install mariadb-server mariadb sudo systemctl start mariadb sudo systemctl enable mariadb sudo mysql_secure_installation
```

#### 4. Install PHP

```bash
sudo yum install php php-mysql sudo systemctl restart httpd
```

#### 5. Verify the Setup

```bash 
sudo nano /var/www/html/info.php
```

Add following content:

```php
<?php
phpinfo();
?>
```
Visit http://your-server-ip/info.php to verify.

#### 6. Clean Up

```bash
sudo rm /var/www/html/info.php
```

## 3.3 Arch Linux

#### 1. Update the System

```bash
sudo pacman -Syu
```

#### 2. Install Apache

```bash
sudo pacman -S apache sudo systemctl start httpd sudo systemctl enable httpd
```

#### 3. Install MySQL/MariaDB

```bash
sudo pacman -S mariadb sudo mariadb-install-db--user=mysql --based=/usr --datadir=/var/lib/mysql sudo systemctl start mariadb sudo systemctl enable mariadb sudo mysql_secure_installation
```

#### 4. Install PHP

```bash
sudo pacman -S php php-apache sudo nano /etc/httpd/conf/httpd.conf
```

Add:

```
LoadModule php_module modules/libphp.so Include conf/extra/php_module.conf
```

Restart Apache:

```bash
sudo systemctl restart httpd
```

#### 5. Verify the Setup 

```bash
sudo nano /srv/http/info.php
```

Add:

```php
<?php
phpinfo();
?>
```

Visit http://your-server-ip/info.php to verify.

#### 6. Clean Up

```bash
sudo rm /srv/http/info.php
```

#### 4. Conclusion
This README provides a comprehensive guide for setting up a LAMP stack on varios Linux distributions. Regardless of the distribution you choose, you can now deploy a basic web server and prepare for further development or testing.

#### 5. References
- [Debian/Ubuntu Documentation](https://wiki.debian.org/LAMP)
- [RedHat/CentOS Documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/)
- [Arch Linux Wiki](https://wiki.archlinux.org/)

#### THANK YOU!
