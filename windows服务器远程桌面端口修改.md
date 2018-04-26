#windows服务器远程桌面端口修改

<!-- more -->

##第一步
打开注册表 win+R regedit 
  
```bash
1:HKEY_LOCAL_MACHINE/System/CurrentControlSet/Control/Terminal Server/WinStations/RDP-Tcp
2:HKEY_LOCAL_MACHINE/SYSTEM/CurrentControlSet/Control/Terminal Server/Wds/rdpwd/Tds/tcp 
```
分别找到 “PortNumber”，用十进制方式显示，默认为3389，改为任意可用端口 



##第二步 
防火墙高级管理-选入站规则-远程桌面用户模式（TCP-IN）选中 
新建规则-端口-应用于TCP，特定本地端口，填写端口号-允许连接，然后全部下一步,名称随便。停用之前3389的端口规则。 
##第三步
重启服务器。


