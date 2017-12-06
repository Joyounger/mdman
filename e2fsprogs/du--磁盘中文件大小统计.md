Summarize disk usage of the set of FILEs, recursively for directories.  

du常用于评估目录所占容量  
用法:du [-ahskm] 文件或目录名称


选项 | 含义
---|---
-a | 列出所有的文件目录与容量,默认仅显示当前目录下的所有文件夹不统计文件
-h | 以人们较易读的容量格式(C/M)显示
-s,--summarize | 列出总量,不列出每个各别的目录占用容量
-S,--separate-dirs | 不包括子目录下的总计
-k | 以KB列出容量显示
-m | 以MB列出容量显示




经验技巧  
1 默认输出的大小单位为1KB