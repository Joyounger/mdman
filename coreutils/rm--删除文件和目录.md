



选项 | header 2
---|---
--preserve-root | do not remove '/' (default) 不删除根目录
--no-preserve-root | do not treat '/' specially
--one-file-system | when removing a hierarchy recursively, skip any directory that is on a file system different from that of the corresponding command line argument


   
   
 



经验技巧  
1 用rm删除的文件仍然可能会被恢复,用shred 可以保证删除的文件完全不可恢复  
Note that if you use rm to remove a file, it might be possible to recover some of its contents, given sufficient expertise and/or time.  For greater assurance that the contents are truly unrecoverable, consider using shred.  

2 删除一个文件名以 '-'开头的文件  
To remove a file whose name starts with a '-', for example '-foo', use one of these commands:  
rm -- -foo  
rm ./-foo  