sed - stream editor for filtering and transforming text  
Sed  is a stream editor.  A stream editor is used to perform basic text
transformations on an input stream (a file or input from  a  pipeline).   
sed是一个非交互性文本流编辑器,可以在命令行输入sed命令，也可以在一个文件中写入命令，然后调用sed，这与awk基本相同。使用sed需要记住的一个重要事实是，无论命令是什么，sed并不与初始化文件打交道，它操作的只是一个拷贝，然后所有的改动如果没有重定向到一个文件，将输出到屏幕。  
因为sed是一个非交互性编辑器，必须通过行号或正则表达式指定要改变的文本行。

sed [-nefr] [动作]  
如果没有 -e, --expression, -f 或 --file 选项，那么第一个非选项参数被视为
sed脚本。其他非选项参数被视为输入文件，如果没有输入文件，那么程序将从标准
输入读取数据。 

选项 | 含义
-- | --
-n | 使用安静模式,只有经过sed特殊处理的那一行才会被列出
-e | 直接在命令行模式上进行sed的动作编辑.允许多重编辑,比如
sed -e '...' -e '...' -e '...'
-f file | 执行文件中指定的sed动作
-r | sed动作支持扩展型正则表达式语法
-i | 直接修改读取的文件内容,而不得由屏幕输出

动作说明: [n1][n2]function
n1,n2: 不见得会存在,一般代表进行动作的行数.

function有下面参数:
参数 | 含义
-- | --
a | 新增, a的后面可以接字符串,而这些字符串会在新的一行出现(目前的下一行)
c | 替换,c的后面可以接字符串,这些字符串可以替换n1,n2之间的行!
d | 删除
i | 插入,i后面可以接字符串,(目前的上一行)
p | 打印,将某个选择的数据打印出来,通常p与sed -n一起用
s | 替换,可直接进行替换的工作.s的参数可以用正则表达式.

实例:  
1 将/etc/passwd内容列出并且打印行号,同时将2-5行删除
$nl /etc/passwd | sed '2,5d'

2 将/etc/passwd内容列出并且打印行号,同时在第二行后加上"drink tea"  
$nl /etc/passwd | sed '2a drink tea'

3 增加多行
$ cat -n /etc/nsswitch.conf | sed -e '2a test \
> test2'

以行为单位的替换与显示  
将第2-5行内容替换为"No2-5 number"
4 $ nl /etc/nsswitch.conf | sed -e '2,5c No 2-5 number'
     1  # /etc/nsswitch.conf
No 2-5 number
     6  #
     7  # Defaults:
     8  # passwd:   files db
     9  # group:    files db
    10  # db_enum:  cache builtin
    11  # db_home:  /home/%U
    12  # db_shell: /bin/bash
    13  # db_gecos: <empty>
    
5 只列出文件的第5-7行
$ nl /etc/nsswitch.conf | sed -n '5,7p'
     5  #    see https://cygwin.com/cygwin-ug-net/ntsec.html#ntsec-mapping-nsswitch
     6  #
     7  # Defaults:


部分数据的查找与替换  
sed还可以用行为单位进行部分数据的查找与替换,与vi类似  
sed 's/要被替换的字符串/新的字符串/g'
一个取得ip地址的实例  
ifconfig | grep 'inet addr' | sed 's/^.*addr://g' | sed 's/Bcast.*$//g' 



直接修改文件内容  
将文件内每一行结尾的.换成!
$ sed -i 's/\.$/\!/g' file
直接在文件最后一行加入"# this is a test"
sed -i '$a # this is a test' file  
其中$代表问价最后一行


