


选项 | 含义
---|---
-E | 使用扩展的正则表达式解释匹配模式，与egrep功能相同
-F | 将匹配模式当做固定字符串，与fgrep相同
-G | 使用基本规则表达式解释匹配模式
-h，--no-filename | 当搜索多个文件时，显示匹配行，不显示该行所属文件名
-H，--with-filename | 搜索多个文件时，显示匹配的行，并显示改行所属文件名
-i | 忽略大小写
-n | 显示匹配行行号
-s | 当文化部不存在或不可读时，
-v | 搜索不含指定字符串的行
-w | 整个单词匹配
-x | 整行匹配
-c | 统计符合匹配模式的行数
-v/--invert-match | 反转查找Invert the sense of matching, to select non-matching lines.













经验技巧  
1 排除空行  
grep -v '^$' filename  
排除以#开头的注释  
grep -v '^#' filename  
排除空行又排除注释行  
grep -v '^$|#' filename
2 grep搜索时包括或排除文件:
只在目录中递归搜索所有的.c和.cpp
grep "main()"  . -r --include *.{c.cpp}
some{str1,str2,str3}会扩展成somestr1,somestr2,somestr3.
3 grep的静默输出:-q
4 打印出匹配文本之前或之后的行:
seq 10 | grep 5 -A 3 #打印某个结果之后的3行
seq 10 | grep 5 -B 3 #打印某个结果之前的3行
seq 10 | grep 5 -C 3 # 打印之前和之后3行



