 tr - translate or delete characters,删除一段信息中的文字,或者进行文字转换  
 用法  
 tr [opt] SET1 ...  
 
 opt | 含义
 -- | --
 -d | 删除信息中的SET1
 -s | 替换掉重复的字符
 
 
 
 
 用法  
 1 将last输出信息中所有小写字符转换为大写
 $ last | tr '[a-z]' '[A-Z]'  
WTMP BEGINS THU MAR 30 17:58:23 2017  

2 取出dos换行符中的\r 