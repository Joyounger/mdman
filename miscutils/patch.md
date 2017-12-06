用法  
patch -p 数字 < patch_file  
假设在patch_file第一行是这样  
***/home/guest/example/expatch.old
那么当我执行"patch -p0 < patch_file"时,更新的文件为/home/guest/example/expatch.old  
如果执行patch -p1 < patch_file时,更新的文件为home/guest/example/expatch.old  
如果执行patch -p4 < patch_file时,更新的文件为expatch.old
也就是说-p num中的num代表拿掉几个斜线/的意思 




1 更新  
patch -pN < patch_file 

2 还原  
patch -R -pN < patch_file 



选项 | 含义
---|---
-p | 后面的N表示取消几层目录的意思
-R | 还原,将新文件还原成旧版本


