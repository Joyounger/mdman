用法  
paste [-d] file1 file2  
paste将文件两行直接连在一起,中间默认以tab分隔


选项 | 含义
---|---
-d | 后面可接分隔字符,默认是以[tab]来分隔的
- | 如果file部分写成-,表示来自standard input的数据的意思


用法  
1 将/etc/group读出,然后与passwd,shadow贴在一起  
$ sudo cat /etc/group | sudo paste /etc/passwd /etc/shadow - | head -n 3      
root:x:0:0:root:/root:/bin/bash root:*:17255:0:99999:7:::       root:x:0:      

daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin daemon:*:17255:0:99999:7:::     daemon:x:1: 

bin:x:2:2:bin:/bin:/usr/sbin/nologin    bin:*:17255:0:99999:7:::        bin:x:2:  
