cut处理的输入都是以行为单位,主要用于将同一行里的数据进行分解,cut在处理多空格相连的数据时可能比较吃力


选项 | 含义
---|---
-d | 后面接分割字符
-f | 依据-d的分隔字符将一段信息切割为数段,用-f取出第几断,多个段之间用逗号分隔
-c | 以字符为单位取出固定字符区间



示例  
1 $ echo $PATH  
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/mnt/c/ProgramData/Oracle/Java/javapath_target_4231216984:/mnt/c/Windows/System32:/mnt/c/Windows:/mnt/c/Windows/System32/wbem:/mnt/c/Windows/System32/WindowsPowerShell/v1.0:/mnt/c/Program Files/Java/jdk1.8.0_144/bin   
$ echo $PATH | cut -d ':' -f 5  
/sbin  


2 将export输出信息中declare -x以后的所有输出提取出来
$ export  
declare -x HOME="/home/kolya"  
declare -x HOSTTYPE="x86_64"  
declare -x LANG="zh_CN.UTF-8"  


export | cut -c 12- 将12个字符及以后的输出提取出来  
HOME="/home/kolya"  
HOSTTYPE="x86_64"  
LANG="zh_CN.UTF-8"  
还可以指定某个范围,如cut -c 12-20