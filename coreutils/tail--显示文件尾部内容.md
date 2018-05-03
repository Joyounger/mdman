tail与head相反
用法  
tail [opt] 文件  
 


选项 | 含义
---|---
--retry | 即使在tail启动时，文件不可访问或文件稍后变的不可访问，都始终尝试打开文件，使用此选项需要与选项--follow=name连用
-c <N> | 输出文件尾部的N个字符  
-f/--follow <name/descriptor> | 持续显示文件最新追加的内容,直到ctrl+C结束 name指定文件名.descriptior指定文件描述符
-n <N> | 输出文件尾部N行内容
--pid=<进程号> | 与-f选项连用时,当指定进程号的进程终止时,自动退出tail指令




经验技巧
1 tail的-f选项可以实时监控文件内容的增长,适合监控日志文件的变化  
tail -f /var/log/messages
dmesg | tail -f
tail -f也可以加入一个睡眠间隔-s,这样就可以设置监视文件更新的时间间隔.
2 当使用-f name监视文件时,如果在监视过程中文件名发生了变化,则失去监视功能.当使用-f descriptor监视文件时,文件名变化后仍然能监视未见内容变化  
3 tail默认也显示10行  
4 tail有个很有意思的特性,当某个给定进程结束后,tail也随之结束.
假设进程foo一直向该文件追加数据,那么tail -f就会一直执行,直到进程foo结束.
PID=$(pidof foo)
tail -f file --pid $PID







