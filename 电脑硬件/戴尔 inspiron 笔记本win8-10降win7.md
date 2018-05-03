# 戴尔 inspiron 笔记本win8/10降win7

<!-- more -->

一: 进BIOS
    
    进入设置->更新和安全->恢复->立即重启->疑难解答->高级选项->UEFI固件设置

二： BIOS设置兼容win7模式

    1.Secure Boot 改为 Disabled
    2.Boot List Option 改为 Legacy
    3.Advanced Boot Options 勾选 enbale roms
    
    如果2，3无法勾选：security->PPT security取消勾选PPT on
    
二： 从U盘启动

    提前准备好带PE的U盘

三：分区
    
    使用软件diakgenuis，删除所有分区，更改磁盘为guid格式转换成mbr格式，新建分区
    
四：重装系统

    正常流程重装


