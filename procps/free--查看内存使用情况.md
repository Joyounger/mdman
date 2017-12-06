

用法:  
 free [options]  
直接执行free以KB为单位显示


options | 含义
---|---
-b | 以Byte为单位显示
-k | 默认,以KB为单位显示
-m | 以MB为单位显示
-g | 以GB为单位显示
-t | 显示物理内存与swap总量


示例  
1 
$ free  
     total   use     free    shared buff/cache available
Mem: 6201188  2126892 3837820  17720  236476     3933440
Swap:18874368 6208    18868160

其中Mem这行显示的是物理内存  




