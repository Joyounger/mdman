用法  
1 查看当前掩码
umask(数字形式) 或 umask -S(rwx形式)


umask用来指定当前用户在新建文件和目录时的默认权限值  


经验技巧  
1 创建文件的默认权限为-rw-rw-rw-,目录的默认权限为drwxrwxrwx  
假设umask为022,那么当用户  
创建文件时,权限为 (-rw-rw-rw-) - (-----w--w-) = -rw-r--r--  
创建目录时,权限为 (drwxrwxrwx) - (d----w--w-) = drwxr-xr-x  

2 默认情况下,root的umaks会拿掉比较多属性,root的umask默认为022.一般用户umask默认为002,即保留同用户组的写入权利  
关于umask的默认设置可以参考/etc/bashrc的内容  


