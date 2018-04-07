用法  
sort [opt] [file or stdin]



经验技巧  
1 sort排序的字符与语系的编码有关,如果你需要排序时,建议使用LANG=C来让语系统一  

选项 | 含义
-- | --
-f | 忽略大小写差异
-b | 忽略文件中的前导空白行最前面的空格部分
-d | 指明以字典序进行排序
-M | 以月份的名字来排序
-n | 以纯数字进行排序,默认以文字类型排序
-r | 反向排序
-u,--unique | 相同的数据中,仅出现一行代表
-t | 分隔符,默认使用tab来分隔
-k | 以那个区间(field)来进行排序



使用示例
1 按照数字进行排序:
```sort -n file.txt```
2 逆序排序
```sort -r file.txt```
3 按月份排序
```sort -M file.txt```
4 合并两个已排序过的文件
```sort -m sorted1 sorted2```
5 找出已排序文件中不重复的行
```sort file1.txt file2.txt | uniq```
6 检查文件是否已排序过:
sort -C filename
if [ $? -eq 0 ]; then
  echo sorted;
else
  echo unsorted;
fi
7 按键或列进行排序:
有时要将特定范围内的一组字符作为键,在这种情况下必须明确地将键指定为某个范围内的字符,这个范围可以用键起止的字符位置来表明.
1010hello
2189bab
7464ddffg
sort -nk 2,3 data.txt
sort -nk 1,1 data.txt #用第一个字符作为键






