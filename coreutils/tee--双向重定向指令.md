用法  
tee [opt] file  
tee可以同时将数据流送与文件与屏幕,输出到屏幕的就是stdout,可以让下个命令继续处理  
也就是将stdout转存一份到文件内,并将同样的数据继续送到屏幕去处理  

opt | 含义
-- | --
-a | 以append方式将数据输出到文件


用法  
1 ls /home | tee ~/homefile | more  
将ls的输出存一份到homefile,同时屏幕也有输出  





