用法  
xargs [opt] cmd  

opt | 含义  
-- | --
-0 | 如果输入的stdin含有特殊字符,例如, \, 空格键等,-0参数可以将它还原成一般字符,
-e'str' | 代表EOF,后面可以接一个字符串str,注意'str'与-e连写没有空格,当xargs分析到这个字符串时就会停止继续工作
-p | 执行每个命令的参数时都会询问用户意思
-n | 后接次数,每次cmd执行时使用几个参数
-d, --delimiter=CHARACTER | 指定分隔符

经验技巧  
1 当xargs后面没有接任何命令时,默认是以echo来输出  
2 很多命令不支持管道,只能以命令行参数的形式接收数据,无法通过stdin接受数据流,因此可以通过xargs让该命令引用stdin.xargs能处理stdin并将其转换为特定命令的命令行参数.xargs也可以将单行或多行文本输入转换成其他格式,如单行变多行或多行变单行.
如何将stdin格式化成不同的输出形式以作为参数:
xargs应紧跟在管道操作符之后,以标准输入作为主要的源数据流,它使用stdin并通过提供命令行参数来执行其他命令:command | xargs
将多行输入转换成单行输出:cat example.txt | xargs
将单行输入转换成多行输出:cat example.txt | xargs -n 3
echo "splitXsplitXsplitXsplit"
如何将这些参数传递给命令:

结合find使用xargs:
只要把find的输出作为xargs的输入,就必须将-print0与find结合使用,以字符null('\0')来分隔输出:
find . -type f -name "*.txt" -print0 | xargs -0 rm -f
统计源码中多有C程序文件的行数:
find code_dir -type f -name "*.c" -print0 | xargs -0 wc -l
结合stdin,巧妙运用while语句和子shell:
cat files.txt | ( while read args; do cat $arg; done )
等同于cat files.txt | xargs -I {} cat {}
while循环中可以将cat $arg替换成任意数量的命令,这样我们就可以对同一个参数执行多条命令.







