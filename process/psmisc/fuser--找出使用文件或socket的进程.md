用法  
fuser [选项] file/dir/socket



选项 | 含义
---|---
-u | 除了进程的pid外,还列出该进程的所有者
-m | 后面接的那个文件名会主动上提到该文件系统顶层,对unmount不成功很有效
-v | Verbose mode.  Processes are shown in a ps-like style.
-k | 找出使用该文件/目录的PID,并试图以SIGKILL这个信号给予该PID
-i | 必须与-k配合,在删除pid前询问用户
-signal | 指定杀死进程时所用的信号

输出中ACCESS这一项的含义为    
c:此进程在当前目录下(非子目录)  
e:可被触发为执行状态  
f:是一个被打开的文件  
r:代表顶层目录  
F:该文件被打开了,不过在等待回应中  
m:可能为分享的动态函数库  



示例  
1 找到所有使用到/proc这个文件系统的进程  
fuser -muv /proc  


