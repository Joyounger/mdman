



对目录进行校验,就是对目录中所有文件以递归方式计算,需要用md5deep或sha1deep
md5deep -rl dir > dir.md5
-r 递归
-l 使用相对路径
用下面的命令核实
md5sum -c dir.md5

也可以结合find:
find dir -type f -print0 | xargs -0 md5sum >> dir.md5