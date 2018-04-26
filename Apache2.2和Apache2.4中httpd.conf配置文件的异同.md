# Apache2.2和Apache2.4中httpd.conf配置文件的异同

Windows环境从Apache2.2改成Apache2.4后httpd.conf中的设置异同。

<!-- more -->

##1、权限设定方式变更

2.2使用Order Deny / Allow的方式，2.4改用Require

apache2.2：


```bash
Order deny,allow
Deny from all
apache2.4：
Require all denied
```
此处比较常用的有如下几种：

```bash
Require all denied

Require all granted

Require host xxx.com

Require ip 192.168.1 192.168.2

Require local

```
注意：若有设定在htaccess文件中的也要修改

##2、设定日志纪录方式变更

RewriteLogLevel 指令改为 logLevel

LOGLEVEL设置第一个值是针对整个Apache的预设等级，后方可以对指定的模块修改此模块的日志记录等级

比如：
LogLevel warn rewrite: warn
##3、Namevirtualhost 被移除

##4、需载入更多的模块
开启Gzip在apache2.2中需载入mod_deflate，apache2.4中需载入mod_filter和mod_deflate

开启SSL在apache2.2中需载入mod_ssl，apache2.4中需载入mod_socache_shmcb和mod_ssl

##5、在windows环境建议的设置



```
EnableSendfile Off
EnableMMAP Off
```
当Log日志出现AcceptEx failed等错误时建议设置


```
AcceptFilter http none
AcceptFilter https none
```
说明：Win32DisableAcceptEx在apache2.4中被AcceptFilter None取代

6、Listen设定的调整

以443为例，不可以只设定Listen 443

会出现以下错误：

(OS 10048)一次只能用一个通讯端地址（通讯协定/网路位址/连接) : AH00072: make_sock: could not bind to address [::]:443

(OS 10048)一次只能用一个通讯端地址（通讯协定/网路位址/连接) : AH00072: make_sock: could not bind to address 0.0.0.0:443

AH00451: no listening sockets available, shutting down

AH00015: Unable to open logs

因此需指定监听的IP，可设定多个

例如：


```
Listen 192.168.2.1:443
Listen 127.0.0.1:443
```


