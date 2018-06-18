linux解压版启动方式
``` shell
cd tomcat/bin
./catalina.sh run
# 假如执行时候出现Permission denied
# 就要给bin目录下的sh文件授权
# 给单个sh文件也行
chmod +x bin/*.sh
```
