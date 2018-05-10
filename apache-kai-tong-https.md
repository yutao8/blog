# apache开通https

1. 监听443端口
2. 正常新建站点
3. apache开启`mod_ssl`模块
4. 新建VirtualHost
5. 复制并加入以下

```text
<VirtualHost *:443>
    DocumentRoot "C:\wwwroot\baidu.com"
    ServerName www.baidu.com
    SSLEngine on
    SSLCertificateFile "(path-to-cert)\public.pem" #公钥
    SSLCertificateKeyFile "(path-to-cert)\214297160470343.key"  #私钥
    SSLCertificateChainFile "(path-to-cert)\chain.pem" #证书链
</VirtualHost>
```

