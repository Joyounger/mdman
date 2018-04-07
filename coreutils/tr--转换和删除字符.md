tr - translate or delete characters,删除一段信息中的文字,或者进行文字转换  
用法  
tr [opt] SET1 [SET2]  
将来自stdin的输入字符从set1映射到set2,然后将输出写入stdout.set1和set2是字符类或字符集.如果两个字符集的长度不相等,那么set2会不断重复其最后一个字符,直到长度和set1相同
 
opt | 含义
-- | --
-d | 删除信息中的SET1
-s | 替换掉重复的字符
-c, -C, --complement | 取SET1的补集
 
 
 
 用法  
 1 将last输出信息中所有小写字符转换为大写
 $ last | tr '[a-z]' '[A-Z]'  
WTMP BEGINS THU MAR 30 17:58:23 2017  

2 取出dos换行符中的\r  
cat /root/passwd | tr -d '\r' > /root/passwd.linux  


经验技巧  
1 tr只能通过stdin,无法通过命令行参数来接受输入.
2 tr可使用的字符类,
alnum:字母和数字
alpha:字母
cntrl:控制(非打印)字符
digit:数字
graph:图形字符
lower:
upper:
print:可打印字符
punct:标点符号
space:空白字符
xdigt:16进制字符

常用示例
1 用tr进行数字加密和解密
echo 12345 | tr '0-9' '9876543210' # 87654, 已加密
echo 87654 | tr '9876543210' '0-9' # 12345, 已解密
2 将制表符转成空格
tr '\t' ' ' < file.txt
3 字符集补集,典型用法是从输入文本中将不在补集中的所有字符:
echo hello 1 char 2 next 4 | tr -d -c '0-9 \n'
4 压缩输入中的重复字符
echo "GNU is       not     UNIX. Recursive   right ?" | tr -s ' '
同tr将文件中的数字列表进行相加:
cat sum.txt | echo $[ $(tr '\n' '+' ) 0 ]
tr将'\n'换成'+',因此得到了字符串"1+2+3+...5+",但是在字符串尾部都多了一个操作符+,因此最后追加一个0.


