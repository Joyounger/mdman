用法:  
declare [选项] variable  
declare [-aAfFgilnrtux] [-p] [name[=value] ...]

选项 | 含义
---|---
-a | 将variable定义为数组类型(array)
-i | 将variable定义为整数数字类型(interger)
-x | 将variable变成环境变量,相当于export variable
-r | 将变量设置为readonly类型,该变量不可被更改内容,也不能重设
-p | 输出variable的属性和值





经验技巧  
1 不带任何选项和参数执行,输出的时所有变量的名称与内容  
2 如果不小心将变量设为只读,一般只能注销再登陆才能回复该变量的类型  
3 将-变成+可以取消操作

示例  
1  用delcare进行整数运算
```
~$ declare -i sum  
~$ sum=10+30  
~$ echo $sum 
40  
~$ declare -x sum  
~$ export | grep sum  
declare -ix sum="40" 
~$ declare +x sum  
~$ declare -p sum  
declare -i sum="40"
```
bash中变量类型默认定义为"字符串"  
bash中的数值运算,默认最多仅能达到整数类型,所以1/3默认的结果为0

2 