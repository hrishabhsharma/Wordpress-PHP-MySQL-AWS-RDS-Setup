### Wordpress-PHP-MySQL-AWS-RDS-Setup
#
 
 #### **Requirements**
 #

* Installing Apache httpd Webserver
```
dnf install httpd -y
```

* epel-release
```
dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm -y
```

* Remi repo is a free and stable YUM repository mainly for the PHP 
```
dnf install https://rpms.remirepo.net/enterprise/remi-release-8.rpm -y
```


* Installing php-7.4
```
dnf module install php:remi-7.4

dnf install php-mysqlnd -y
``` 

* To download the WordPress installation package
```
wget https://wordpress.org/latest.tar.gz
```
* extracting package and copying wordpress folder to document root /var/www/html
```
tar -xvzf latest.tar.gz -C /var/www/html 
```

* Permissions:
```
chown -R apache:apache /var/www/html/wordpress
chcon -t httpd_sys_rw_content_t /var/www/html/wordpress -R
```

* Create MySQL Database on AWS using RDS Service

* MYSQL Installation
```
dnf install mysql -y
```

* MySQL login
```
mysql -h endpoint -u -p
```

* Starting httpd Services

* Connecting with WordPress
