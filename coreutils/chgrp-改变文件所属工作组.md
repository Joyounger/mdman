
用法：  
1 chgrp [选项]... 用户组 文件...  
Change the group of each FILE to GROUP.  

2 chgrp [选项]... --reference=参考文件 文件...  
With --reference, change the group of each FILE to that of RFILE.  




header 1 | header 2
---|---
-c | 显示文件所属组的改变,like verbose but report only when a change is made
-f, --silent, --quiet | suppress most error messages
 -v, --verbose | 
-R, --recursive | 递归 
--reference=RFILE | 把执行文件所属工作组改为与制定模板文件所属工作组相同 use RFILE's group rather than specifying a GROUP value




经验技巧:  
1 使用组id可以达到与使用组名相同的效果
