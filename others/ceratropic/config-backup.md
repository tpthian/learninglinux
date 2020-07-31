[\[back\]](../ceratropic)

# Configure the backup

Assuming the starting working directory (ceratropic) is the backup folder from top
level.

[1]. Re-configure the database server

```bash
[ceratropic] cd config
[config] vi settings.inc.php
```
then change the following variable according to the server settings

```php
<?php
define('_DB_SERVER_', '[your-hostname]');
#[...]
define('_DB_NAME_', '[your-db-name]');
define('_DB_USER_', '[your-mysql-user]');
define('_DB_PASSWD_', '[your-db-password]');
#[...]
?>
```

[2]. Open smarty debug console
```bash
[config] vi smartyadmin.config.inc.php

# online 28, change the default `false` to `true`
global $smarty;
// false, no debugging 
$smarty->debugging = true;
[...]
```

[3]. Enable debug in prestashop
```bash
[config] vi defines.inc.php
```
```php
[...]
/* Debug only */
/* change false -> true */
if (!defined('_PS_MODE_DEV_')) {
    define('_PS_MODE_DEV_', true);
}
[...]
```

