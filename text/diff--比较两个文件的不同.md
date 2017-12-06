
用法:  
diff [选项] from-file to-file
from-file是要用来比较的文件  
to-file就是from-file要对比的基准文件
from-file和to-file可以用"-"代替,代表标准输入


选项 | 含义
---|---
-b | 忽略一行当中仅有多个空白的区别(如"about me"和"about    me"视为相同)
-B | 忽略空白行的区别
-i | 忽略大小写的不同



经验技巧  
1 diff还可以比较两个目录的区别