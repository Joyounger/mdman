time [option] comand [arguments...]  

time命令会将命令的执行时间添加到stderr中
输出中:
real:挂钟时间,就是从开始到结束的时间.这段时间包括其他进程所占用的时间片以及进程被阻塞所花费的时间(如为等待i/o操作完成所花费的时间).
user:指进程花费在用户模式中的cpu时间.这是唯一真正用于执行进程所花费的时间.执行其他进程以及花费在阻塞状态中的时间并没有计算在内.
sys:指进程花费在内核模式中的cpu时间.它代表在内核中执行系统调用所花费的时间.




经验技巧:
1 执行time时默认执行的是shell的内建命令time,而不是/usr/bin/time.
shell的内建命令选项有限,如果需要更多功能就需要/usr/bin/time.
可以使用选项-o将命令执行时间写入文件:
/usr/bin/time -o output.txt cmd
可以用-f格式字符串格式化时间输出:
real -%e
user -%U
sys -%S
eg:
/usr/bin/time -f "Time:%U" -o file cmd
通过/usr/bin/time命令可以获得进程的很多细节信息,每个参数都可以用合适的格式字符串显示
选项|含义
---|---
%C | 命令名称及命令行参数
%D | 进程非共享区域数据的大小,以KB为单位
%E | 进程使用的real时间(挂钟时间).显示格式为[小时:]分:秒
%x |  Exit status of the command
%k | Number of signals delivered to the process.
%W | Number of times the process was swapped out of main memory.
%Z | System's page size, in bytes.  This is a per-system constant, but varies between systems.
%P | Percentage of the CPU that this job got.  This is just user + system times divided by the total running time(等于user+sys再除以总共运行时间). It also prints a percentage sign(结果以百分比显示)
%K | Average total (data+stack+text) memory use of the process, in Kilobytes.
%w | Number of times that the program was context-switched voluntarily, for instance while waiting for an I/O operation to complete. 
%c | Number of times the process was context-switched involuntarily (because the time slice expired).







