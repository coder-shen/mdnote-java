* 查看方式
> show VARIABLES like '%max_allowed_packet%'

* 设置命令
> set global max_allowed_packet = 2*1024*1024*10

* 配置文件方式
> 找到mysql安装目录，如果是windows的话 就是MySQL Server x.x 下面，修改my.ini文件中对于的配置项。如果my.ini不存在，那么就复制 my-default.ini,修改名字为my.ini然后再修改对于的配置项```配置之后要重新启动Mysql服务，要注意有时候my.ini的目录并非是之前说的这个目录，可能是在ProgramData里面，具体是哪个路径，看服务的属性的可执行文件路径后面的default-file属性```