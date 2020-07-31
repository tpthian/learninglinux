[\[back\]](../..)
# `httpd` installation

[1]. Install httpd

```bash
~ sudo dnf -y install httpd
```

[2]. Configure httpd.

```bash
~ sudo vi /etc/httpd/conf/httpd.conf

# line 151
AllowOverride All

# line 164
DirectoryIndex index.html index.cgi index.php

```

[3]. Change ownership of `/var/www/html` directory

```bash
# Make sure the user:group ownership belong to apache:apache
~ sudo chown -R apache:apache /var/www/html

# Make sure that from now on, whatever goes inside this folder belong to
# the group `apache`
~ sudo chmod g+s /var/www/html
```

[4]. Start httpd

```bash
# start httpd
~ sudo systemctl start httpd

# enable httpd to start when startup
~ sudo systemctl enable httpd
```

