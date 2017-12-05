Change the SELinux security context of each FILE to CONTEXT.    


用法:   
chcon [选项]... 环境 文件...  
chcon [选项]... [-u 用户] [-r 角色] [-l 范围] [-t 类型] 文件...  
-u 后面接身份标识,如system_u  
-t 后面接安全上下文的类型字段,如httpd_sys_content_t;  
-r 后面接角色,如system_r  
chcon [选项]... --reference=参考文件 文件...  
--reference=参考文件:拿某个文件当范例来修改后续接的文件的类型





选项 | 含义
---|---
-R | 递归

