用法  
gzip [选项] 文件名  

gzip可以解开zip格式

选项 | 含义
---|---
-c | 将压缩数据输出到屏幕上,可通过数据流重定向来处理
-d | 解压缩
-t | 检测压缩文件是否损坏
-v | 可显示压缩文件的压缩比信息
-<n> | 压缩等级,1最快,9最慢


经验技巧  
1 gzip压缩时默认会删除源文件,如果想保留压缩前的源文件, 可以用-c将源文件数据重定向到新文件
gzip -c filename > filename.gz


zcat类似cat,直接读取.gz压缩文件中的原始文件  
用法  
zcat [OPTION]... [FILE]...  
Uncompress FILEs to standard output.  