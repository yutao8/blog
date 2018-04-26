# MAC下安装MAMP的PHPredis扩展

<!-- more -->

1. 下载phpredis扩展安装包。git clone https://github.com/nicolasff/phpredis.git；
2. 解压,进入该目录,依次执行以下操作；
3. `/Applications/MAMP/bin/php/php5.6.30/bin/phpize` ([PHP编译扩展出现Cannot find autoconf的解决方法](mweblib://15143433921449))
4. `./configure --with-php-config=/Applications/MAMP/bin/php/php5.6.30/bin/php-config`
5. `make`
6. `make install`
7. 安装成功后将`./modules/redis.so`会复制到`Applications/MAMP/bin/php/php5.6.30/modules`目录下。
8. 配置mamp php.ini 
9. 保存,mamp自动重启,测试ok;
![-w405](media/15143435929117/15143445006202.jpg)

![](media/15143435929117/15143448146198.jpg)

![](media/15143435929117/15143448369550.jpg)





