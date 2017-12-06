
gzip与bzip2虽然能对目录操作,但这两个命令对目录的压缩指的是将目录内的所有文件分别进行压缩.


bzip2 用于压缩文件  
用法:bzip2 [-cdkzv#] 要压缩的文件名

选项 | 含义
---|---
-c | 将压缩过程产生的数据输出到屏幕上
-d | 解压缩,相当于bunzip2
-z | 压缩
-k | 不删除被压缩文件
-v | 输出详情
-s | 使用较少的内存

用法:
bzip2 -z man.config
将man.config压缩为man.config.bz2

bzcat man.config.bz2
将man.config.bz2的文件内容读出来

bzip2 -d man.config.bz2
解压缩man.config.bz2
















