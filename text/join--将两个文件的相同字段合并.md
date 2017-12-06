用法  
join [选项] file1 file2  

join适合于处理两个相关的数据文件

选项 | 含义
---|---
-t char | 指定char为分隔符
-i,--ignore-case | 忽略大小写
-1 字段 | 第1个文件用哪个字段来分析
-2 字段 | 第2个文件用哪个字段来分析  


经验技巧  
1 join默认以空格分隔数据,并且对比"第一个字段的数据",如果两个文件相同,则将两条数据练成一行,且第一个字段放在第一个;  
2 使用join之前你所需要处理的文件应该要事先经过排序(sort)处理,否则有些对比的项目会被略过



示例  
1 将/etc/passwd 和 /etc/shadow 相关数据整合成一列
$ sudo head -n 3 /etc/passwd /etc/shadow  
[sudo] kolya 的密码：  
==> /etc/passwd <==  
root:x:0:0:root:/root:/bin/bash  
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/  
bin:x:2:2:bin:/bin:/usr/sbin/nologin  

==> /etc/shadow <==  
root:*:17255:0:99999:7:::  
daemon:*:17255:0:99999:7:::  
bin:*:17255:0:99999:7:::  

join -t ':' /etc/passwd /etc/shadow

2 /etc/passwd的第四个字段为gid,那个gid记录在/etc/group当中的第三个字段  
join -t ':' -1 4 /etc/passwd -2 3 /etc/shadow
