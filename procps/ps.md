



选项 | 含义
---|---
-A | 所有进程均显示出来,与-e具有同样作用
-a | 显示不与terminal有关的进程
-u | 有效用户(effective user)相关的进程
-x | 通常与-a一起使用,列出完整信息
-l | 每个进程按长格式列出
-j | 
-f | 做一个更完整的输出





示例  
1 ps aux 查看系统所有进程数据  
在ps aux输出中: 
TTY:若与终端机无关则显示?, 另外tty1-tty6是本机上面的登陆者程序,若为pts/0等则表示为由网络连接进主机的进程.  
START:进程的启动时间
TIME:进程实际使用cpu运行的时间  

2 ps -l 仅查阅自己bash相关的进程  
ps -l输出中: 
F 代表进程标志,常见取值有:  
4 进程权限为root  
1 此子进程仅可以进程复制,而无法实际执行
S 进程状态,常见取值有:  
R:running
S:sleep,正在睡眠,但可被唤醒  
D:不可被唤醒的睡眠状态,通常这个进程可能在等待i/o的情况  
T:stop,停止状态,可能是job   control(后台暂停)或除错(traced)状态    
Z:zombie, 僵尸进程  
UIP:进程拥有者的user id  
PPID:进程的府进程的pid  
C:cpu使用率,单位为百分比  
PRI/NI:priority/nice的缩写  
ADDR:进程在内存哪个部分,如果进程为running状态则显示"-"  
SZ:进程用掉多少内存  
WCHAN:目前进程是否运行中,若为-表示正在运行中.  
TTY:登陆者的终端机位置,若为远程登陆则使用动态终端接口(pts/n)  
TIME:使用掉的cpu时间  
CMD:触发此进程的命令  

3 列出类似进程树的进程显示  
ps axjf  

经验技巧  
1 cmd后面如果有<defunct>字样,则此进程为僵尸进程

















