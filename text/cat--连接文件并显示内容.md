cat是concatenate(连接)的简写,将一个文件内容连续输出到屏幕上

cat命令的用途是连接文件或标准输入并打印。这个命令常用来显示文件内容，或者将几个文件连接起来显示，或者从标准输入读取内容并显示，它常与重定向符号配合使用。  

cat主要有三大功能：  
1.一次显示整个文件:cat filename  
2.从键盘创建一个文件:cat > filename 只能创建新文件,不能编辑已有文件.  
3.将几个文件合并为一个文件:cat file1 file2 > file
cat file1 file2 #将多个文件内容拼接在一起输出  


使用here doc来生成文件  
[root@localhost test]# cat >log.txt <<EOF  
> Hello  
> World  
> Linux  
> PWD=$(pwd)  
> EOF  
[root@localhost test]# ls -l log.txt   
-rw-r--r-- 1 root root 37 10-28 17:07 log.txt  
[root@localhost test]# cat log.txt   
Hello  
World  
Linux  
PWD=/opt/soft/test  
[root@localhost test]#
说明：
注意粗体部分，here doc可以进行字符串替换。  


选项 | 功能
-- | --
-b | 只在非空行前显示行号,会覆盖-n
-n | 显示所有行号，包括空行
-s | 压缩空行，多个空行出现时仅显示
-A | 显示所有字符，$代表linux行尾，^M$代表windows行尾,^I代表TAB


经验技巧
1 cat不带选项和参数时，将复制标准输入内容到标砖输出，即输入一行内容后立即将所输入的内容显示到标准输出设备  
2 用cat -A可以区分出文件中的空格和tab, 空格就显示为空格,tab则显示为^I  
3 cat还可以从标准输入中读取需要使用管道操作符
OUTPUT_FROM_SOME_COMMANDS | cat
将来自输入文件的内容与标准输入拼接在一起.将stdin和另一个文件中的数据结合起来.方法如下:
echo 'Text through stdin' | cat - file.txt

