[\[back\]](../..)

# Installing PHP

[1]. Install php7.1

```bash

sudo dnf --enablerepo=remi-safe -y install \
php71 \
php71-php-pear \
php71-php-mbstring \
php71-php-mysqlnd \
php71-php-pecl-mysql \
php71-php-pecl-mysql-xdevapi \
php71-php-fpm \
environment-modules-3.2.10-0 \
php71-php-cli-7.1.33-8 \
php71-php-common-7.1.33-8 \
php71-php-json-7.1.33-8 \
php71-php-pdo-7.1.33-8 \
php71-php-process-7.1.33-8 \
php71-php-xml-7.1.33-8 \
php71-runtime-2.0-1 \
protobuf-2.5.0-8.el7.x86_64 \
tcl-1:8.5.13-8.el7.x86_64

```

[2]. Next, configure PHP-FPM

```bash
sudo vi /etc/httpd/conf.d/php.conf
```

[3]. Start PHP-FPM

```bash
# start 
~ sudo systemctl start php71-php-fpm

# enable start with startup
~ sudo systemctl enable php71-php-fpm

# restart apache server
~ sudo systemctl restart httpd

```

[4]. Create a test file

```bash
~ echo '<?php phpinfo(); ?>' > /var/www/html/info.php
```


