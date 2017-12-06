相比于sed常用于一整行的处理,awk则比较倾向于将一行分成数个字段来"处理"  
awk主要是处理每一行的字段内的数据,而默认的字段的分隔符为空格键或[tab]键.


awk通常运行模式为  
awk后面接两个单引号加上大括号{}来设置想要对数据进行的处理动作:  
awk '条件类型1{动作1} 条件类型2{动作2} ...' filename  
{}内的动作如果需要多个辅助可利用;分隔  
{}内的动作支持if

awk也可读取来自前个命令的标准输出

awk默认的字段分隔符为空格或tab  
**awk是以行为一次处理的单位,而以字段为最小的处理单位**  
每一行的第一个字段为$1,依次类推,$0则代表一整行数据



awk的内置变量
名称 | 意义
---|---
NF | 每一行($0)拥有的字段总数
NR | 目前awk所处理的是"第几行"数据
FS | 目前的分隔字符,默认为空格或tab


用法示例:  
1  
$ last -n 5  
wtmp begins Thu Mar 30 17:58:23 2017  
~$ last -n 5 | awk '{print $1 "\t" $3}'  
wtmp    Thu


2 
last -n 5 | awk '{print $1 " line " NR ","}'


3 与shell不同,awk中变量可以直接使用,不加$  
列出每一行的账号,也就是$1  
列出目前处理的行数($1)  
列出目前处理的行数(NR)  
该行有多少字段(NF)  
$ last -n 5 | awk '{print $1 ": line " NR ", ", NF " columes"}'  
: line 1,  0 columes  
wtmp: line 2,  7 columes  
注意printf的格式中非变量的文字部分都要使用双引号  


4 
$ cat /etc/passwd | awk '{FS=":"} $3 < 100 {print $1 "\t" $3}'  
root:x:0:0:root:/root:/bin/bash(读入第一行时变量还是默认以空格键为分隔导致)  
daemon  1  
bin     2  
sys     3  
sync    4  
games   5  
man     6  
lp      7  
mail    8  
news    9  
uucp    10  
proxy   13  
www-data        33  
backup  34  
list    38  
irc     39  
gnats   41  



$ cat /etc/passwd | awk 'BEGIN {FS=":"} $3 < 100 {print $1 "\t" $3}'  
root    0  
daemon  1  
bin     2  
sys     3  
sync    4  
games   5  
man     6  
lp      7  
mail    8  
news    9  
uucp    10  
proxy   13  
www-data        33  
backup  34  
list    38    
irc     39  
gnats   41  


$ cat pay.txt  
Name    1st     2nd     3th  
VBird   23000   24000   25000  
DMTsai  21000   20000   23000  
Bird2   43000   42000   41000  

如何计算每个人的总额  
kolya@asusn43sl ~/src/vbird/text  
$ cat pay.txt | awk 'NR==1 {print $1 "\t" $2 "\t" $3 "\t" $4 "\t" "Total"} NR>=2 {print $1 "\t" $2 "\t" $3 "\t" $4 "\t" $2+$3+$4}'  
Name    1st     2nd     3th     Total  
VBird   23000   24000   25000   72000  
DMTsai  21000   20000   23000   64000  
Bird2   43000   42000   41000   126000  


利用printf格式化输出时要加上"\n"才能分行
