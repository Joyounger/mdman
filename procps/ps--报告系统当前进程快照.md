


不带任何参数执行ps,ps将显示运行在当前终端(tty)中的命令




选项 | 含义
---|---
-f,--full | Generate a full listing.
-e, --everyone | show processes of all users
-x | 解除由ps默认添加的tty限制.
-o | 指定想要显示的列




经验技巧
1 -o的参数以逗号分隔,逗号与它分隔的参数之间是没有空格的.在大多数情况下,-o都是和选项-e(every)结合使用的
但如果-o需要使用某些过滤器,例如列出特定用户拥有的进程,那么就不再使用-e.-e和过滤器结合依旧会显示所有进程
-o可用的参数
pcput
pid
ppid
pmem
comm
cmd 简单命令(simple cmd),是平时使用最频繁的一种命令,它是空白字符分隔的一系列单词,以shell控制操作符作为结尾.
user
nice
time
etime
tty
euid
stat

2 可以用--sort将ps命令的输出根据特定的列进行排序, 可以在参数前加上+或-来指定排序方式
ps [option] --sort -patameter1,+parameter2,parameter3.
列出占用cpu最多的10个进程
ps -eo comm,pcpu --sort -pcpu | head
3 找出给定cmd对应的进程id
ps -C cmd_name
或
ps -C cmd_name -o pid=
pid后加=将移除ps输出中的头部PID,参数后加上=可移除每一列的头部


4 可以用ps根据指定的用户名或id对进程进行分组,指定的参数可以用来过滤ps的输出:通过检查每一个输出条目是否属于参数列表中指定的有效用户或真实用户,
用-u user1, user2一次类推,指定有效用户列表
用-U user1, user2一次类推,指定真实用户列表


5 用tty过滤ps输出
可以通过指定进程所属的tty选择ps的输出.用-t指定tty列表:
ps -t TTY!, TTY2, ..

6 可以用-L在ps输出中显示线程的相关信息.这会显示出两列:NLWP和NLP.NLWP是进程的线程数量,NLP是ps输出中每个条目的线程id

7 显示进程的环境变量:
ps -eo cmd e




