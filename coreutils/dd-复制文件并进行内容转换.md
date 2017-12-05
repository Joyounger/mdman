dd是disk dump的简称

选项 | 功能
--- | ---
if=<输入文件> | 从指定文件中读入信息.如果不指定if,从stdin读入信息
of=<输出文件> | 指定输出文件.否则输出到标准输出设备
ibs=<字节数> | 指定每次输出的字节数,默认值是512字节
obs=<字节数> | 指定每次写入的字节数,默认值是512字节
bs=<字节数> | 指定每次读写的字节数,会覆盖ibs和obs
cbs<字节数> | 为块转换和非块转换指定转换块的字节数
skip=<块数> | 在复制之前,忽略输入文件的最开始指定块数内容,块大小由ibs选项指定
seek=<块数> | 在拷贝之前,跳过输出文件的最开始指定块数内容,块大小由ibs选项指定
count=<块数> | 只拷贝输入文件的前面指定块数内容
conv=<关键字,关键字,...> | 将文件按指定关键字的方式转换(注意在,前后没有空格).支持的转换方式包括:  ascii 将ebcdic吗转换成ascii码  ebcdic 将ascii码转换成ascii码 ibm 将ascii码转换成alternative ebcdic码 block 每一行输入信息,无论其长短,输出都是选项cbs指定的字节数,并且其中的,并且其中的换行用空格替换.如果有必要,行尾填充空格 unblock 用换行替换每个块末尾的空格 lcase 将大写字母转成小写字母 ucase 将小写字母转成大写字母 swab 交换每队输入字节.如果读入的字节数是奇数,最后一个字节只是简单的复制到输出 noerror 当读取信息发生错误时,仍然继续进行 notrunc 对输出文件不进行截断操作 sync 用0填充每个输入块的末尾,使其大小为选型ibs的值



经验技巧  
1 使用dd可以在复制文件的同时对文件内容进行转换或格式化处理
2 dd可以用来制作软盘和光盘镜像
dd if=/dev/cdrom /path/cdrom.iso
dd if=/dev/fd0 /path/floppy
3 用dd可以创建空文件, eg:  
dd if=/dev/zero of=/tmp/zerofile bs=1M count=512



实例:  
1 用dd复制文件并将文件中小写字母全部转化为大写字母
dd if=inp.txt conv=ucase of=out.txt

2 备份文件
$ ls -l /etc/passwd  
-rw-r--r-- 1 root root 1612 7月  12 02:37 /etc/passwd  
$ dd if=/etc/passwd of=/tmp/passwd.bak  
记录了3+1 的读入  
记录了3+1 的写出  
1612 bytes (1.6 kB, 1.6 KiB) copied, 0.006992 s, 231 kB/s  
没有设置bs,默认1个count为512byte,/etc/passwd为1612byte,因此上面的3+1表示有3个完整的512byte,以及不满512byte的另一个block


3 备份磁盘的第一个扇区
dd if=/dev/hdc of=/tmp/mbr.bak bs=512 count=1