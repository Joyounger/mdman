用法  
which [opt] cmd  


opt | 含义
-- | --
-a | 将所有由PATH目录中可以找到的命令均列出,而不只是第一个被找到的命令名称


经验技巧  
1 which是根据执行命令的当前用户设置的PATH变量内的路径去查找可执行文件,因此不同用户找到的命令可能不一样  
2 which查找的是可执行文件,因此查找不到shell内置命令  
$ type -a printf  
printf 是 shell 内建  
printf 是 /usr/bin/printf  
$ which -a printf  
/usr/bin/printf  
3 which后的cmd必须是完整文件名  
