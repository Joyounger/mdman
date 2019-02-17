






经验技巧
1 脚本中可以用ping的返回值判断能否ping通
ping address -c 2
if [ $? -eq 0 ]; then
...


