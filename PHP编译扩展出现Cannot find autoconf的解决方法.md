# PHP编译扩展出现Cannot find autoconf的解决方法

编译redis扩展是遇到`Cannot find autoconf`情况,以下是解决办法:

<!-- more -->


```bash
➜  phpredis-develop /Applications/MAMP/bin/php/php5.6.30/bin/phpize
Configuring for:
PHP Api Version:         20131106
Zend Module Api No:      20131226
Zend Extension Api No:   220131226
Cannot find autoconf. Please check your autoconf installation and the
$PHP_AUTOCONF environment variable. Then, rerun this script.
```

解决办法:

```bash
➜  brew install autoconf
```




