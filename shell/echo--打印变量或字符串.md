

经验技巧  
1 linux下还有一个普通的echo可执行命令   
$ type -a echo  
echo 是 shell 内建  
echo 是 /bin/echo  
$ ls -l /bin/echo -h  
-rwxr-xr-x 1 root root 31K 2月  18  2016 /bin/echo  
根据这个echo命令的manpage描述, 这个命令一般会被shell中的echo代替   
man 1 echo  
NOTE:  your  shell may have its own version of echo, which usually supersedes the version described here.  Please refer to your shell's documentation for details about the options it supports.

