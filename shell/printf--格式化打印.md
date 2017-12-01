用法  
printf [-v var] '打印格式' 实际内容  



打印格式 | header 2
---|---
\a | 发出警告声音
\b | 退格键
\f | 清除屏幕(form feed)
\n | 输出新的一行
\r | 回车enter
\t | 水平tab
\v | 垂直tab
\xNN | NN为两位数数字,可以转换数字成为字符
%ns | n为数字,s为string多少个字符
%ni | n为数字,i为integer,多少个整数字数
%N.nf | n与N都是数字,f为浮点数



经验技巧  
1 shell中的printf一般会覆盖/usr/bin/printf命令  
$ type -a printf  
printf 是 shell 内建  
printf 是 /usr/bin/printf  
man 1 printf  
NOTE:  your shell may have its own version of printf, which usually supersedes the version described here.  Please refer to your shell's documentation for details about the options it supports.