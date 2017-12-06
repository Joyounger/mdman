

1 当待备份数据为单一文件系统  
可以使用完整的dump功能,备份时可以使用挂载点或设备文件来备份
1.1 dump -S /dev/hdc1
1.2 将完整备份的文件名记录成为 /root/boot.dump, 同时更新记录文件:
dump -0u -f /root/boot.dump/boot
1.3 


2 待备份的数据只是目录,并非单一文件系统.
这时备份就有限制:  
1 所有的备份数据都要在该目录下面  
2 只能使用level 0,即仅支持完整备份而已
3 不支持-u,即无法创建/etc/dumpstates这个level备份的时间记录文件
2.1 将整个/etc目录备份
dump -0j -f /root/etc.dump.bz2 /etc





经验技巧:  
1 dump的参数虽然复杂,但如果只是简单的操作,只需要记住下面几个命令  
dump [-Suvj] [level] [-f 备份文件] 待备份数据  
dump -W

选项 | 含义
---|---
-S | 仅列出后面的待备份数据需要有多少磁盘空间才能备份完毕
-u | 将这次dump的时间记录到/etc/dumpdateS文件中
-v | 将dump过程显示出来
-j | 加入bzip2支持,将数据进行压缩,默认bzip2压缩等级为2
-level | 从 -0 到 -9 共十个等级
-f | 有点类似tar, 后面接产生的文件,可接例如/dev/st0设备文件名等
-W | 列出在/etc/fstab里面的具有dump设置的分区是否有备份过





