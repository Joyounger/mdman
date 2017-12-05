用法  
sudo [选项] [-u 新用户账号] cmd  

选项 | 含义 
-- | --
-b | 将后续命令让系统自动执行.不与目前shell产生影响
-u user | 后面可接要切换的用户user, 若无此选项则代表切换身份为root 



经验技巧  
1 相对于su需要了解要切换到的用户密码,sudo的执行仅需要自己的密码.sudo可以让用户以其他用户身份执行命令(一般是作为root执行),因此仅有/etc/sudoers内的用户才能执行sudo这个命令.  
2 root执行sudo时不需要密码  
3 直接编辑/etc/sudoers不合适

示例  
1 无法使用su - username去切换系统账号,因为系统账号的shell是/sbin/nologin,这时使用sudo就很好用