
man -a cmd  在所有的man帮助手册中搜索cmd

<style>  
table th:0 {  
    width: 100px;  
}  
</style>  

选项 | 含义
--- | --
-a | 缺省情况是在显示第一个找到的手册之后，就会停止搜寻，使用此选项会强迫man继续显示所有符合name的联机手册。
-K | search for text in all pages对所有的联机手册搜寻所指定的字串。请注意，本功能回应速度可能很慢，如果指定section（区域）会对速度有帮助。 
-i | 查找手册页时不区分大小写字母(默认)
-I | 查找手册页时区分大小写字母。
--regex |  show all pages matching regex  
--wildcard | show all pages matching wildcard  
--names-only |  make --regex and --wildcard match page names only, not descriptions



使用经验  
1 由于手册页man page是用less程序来看的(可以方便地使屏幕上翻和下翻), 所以在man page里可以使用less的所有选项。   
