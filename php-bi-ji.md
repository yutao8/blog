# PHP笔记

## 2016年2月29日15:26:34

mysql 搜索替换

```sql
UPDATE `wp_auto_reply` SET `content` = REPLACE (`content`,'【直讯通小微】','')
```

反向like

```sql
SELECT * FROM wp_keyword WHERE INSTR('我想入驻赞品城', `keyword` )>0 AND keyword !=''
```

## 2016年1月30日17:58:05

mysql字符串连接

```sql
UPDATE sp_zxt_num SET number = CONCAT('直讯通',number)
```

## 2016年1月26日10:09:11

php 重复输出字符串

```php
<?php echo str_repeat("_",5); ?>
```

输出字符到文件\(追加\)

```php
file_put_contents('log.txt',$str,8);
```

## 2016年1月18日

php截取文章文字前54字

```php
mb_substr(strip_tags($str),0,54,'utf-8');
```

apache 虚拟主机配置

```bash
#Virtual hosts   
Include conf/extra/httpd-vhosts.conf
<Directory "F:\yutao\svn">  
    Options Indexes FollowSymLinks  
    AllowOverride All  
    Order allow,deny  
    Allow from all  
</Directory>  
<VirtualHost 127.0.0.4:80>  
    DocumentRoot F:\yutao\svn  
    ServerName 127.0.0.4  
</VirtualHost>`
```

