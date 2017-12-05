用法  
split [选项] file PREFIX  


选项 | 含义
-- | --
-b <size> | 后面接要切割成的文件大小,可加单位,如b, k, m
-l | 以行数来进行切割
PREFIX | 代表前导符,可作为切割文件的前导文字

经验技巧  
1 With no FILE, or when FILE is -, read standard input.  


示例  
1 将ls -al /输出的信息中,每10行记录成一个文件  
$ ls -al / | split -l 10 - lsroot  
kolya@asusn43sl:~$ wc -l lsroot*  
  10 lsrootaa  
  10 lsrootab  
   6 lsrootac  
  26 总用量  
