bash内置了对整数四则运算的支持，但是并不支持浮点运算，而bc命令可以很方便的进行浮点运算，

一个简单的使用 bc 命令的模版可以用来在计算脚本中的变量. 用在命令替换 中.  
variable=$(echo "OPTIONS; OPERATIONS" | bc)  
如：interest_rate=$(echo "scale=9; $interest_r/12 + 1.0" | bc)  
其中的options就是对bc的设置,如设定计算精度scale等


用bc进制转换,可以通过设置bc的obase和ibase参数实现  
scale defines how some operations  use  digits after the decimal point.  The default value of scale is 0.  
ibase and obase define the conversion base for input and output numbers.  

#!/bin/bash 
abc=192 
echo "obase=2;$abc" | bc  
这是用bc将十进制转换成二进制

abc=11000000   
echo "obase=10;ibase=2;$abc" | bc  
这是用bc将二进制转换为十进制。


