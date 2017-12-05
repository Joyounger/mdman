为basename指定一个路径，basename命令会删掉所有的前缀包括最后一个slash（‘/’）字符，然后将字符串显示出来。

basename命令格式：  
basename [pathname] [suffix]  
basename [string] [suffix]
 
suffix为后缀，如果suffix被指定了，basename会将pathname或string中的suffix去掉。eg:  
$ basename ./include/stdio.h .h  
stdio