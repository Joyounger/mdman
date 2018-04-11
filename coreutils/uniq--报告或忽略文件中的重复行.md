用法  
uniq [opt]


opt | 含义
-- | --
-i | 忽略大小写字符的不同
-c | 进行计数
-u | 只显示唯一的行
-d | 只显示重复的行
-s | 指定可以跳过前n个字符
-w | 指定用于比较的最大字符数
-z, --zero-terminated | line delimiter is NUL, not newline

经验技巧
1 uniq只能作用于排过序肚饿数据输入,因此uniq要么使用管道,要么将排过序的文件作为输入,与sort命令结合使用.




常用实例
1 从给定数据中生成唯一的行:
$ cat sorted.txt
bash
foss
hack
hack
$ uniq sorted.txt 
bash
foss
hack

或者 sort unsorted.txt | uniq
只显示唯一的行:uniq -u sorted.txt 或 sort unsorted.txt | uniq -u
统计各行在文件中出现的次数:sort unsorted.txt | uniq -c
找出文件中重复的行:sort unsorted.txt | uniq -d

2 删除所有指定文件,这些文件的路径从file.txt中读取
uniq -z file.txt | xargs rm
用命令输出作为xargs的输入时,最好为输出的各行添加一个0值字节终止符,因为默认xargs会用空格作为界定符分割参数
