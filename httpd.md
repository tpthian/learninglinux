# `httpd` installation

1. Install httpd

```bash
~ sudo dnf -y install httpd
```

2. Configure httpd.

```bash
~ sudo vi /etc/httpd/conf/httpd.conf

# line 151
AllowOverride All

# line 164
DirectoryIndex index.html index.cgi index.php

```