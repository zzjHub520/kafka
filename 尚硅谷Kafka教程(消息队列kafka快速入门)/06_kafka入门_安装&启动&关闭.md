![image-20211129224645816](MarkDownImages/06_kafka入门_安装&启动&关闭.assets/image-20211129224645816.png)

![image-20211129224715057](MarkDownImages/06_kafka入门_安装&启动&关闭.assets/image-20211129224715057.png)

可选配置

![image-20211129224804707](MarkDownImages/06_kafka入门_安装&启动&关闭.assets/image-20211129224804707.png)

![image-20211129224833703](MarkDownImages/06_kafka入门_安装&启动&关闭.assets/image-20211129224833703.png)

命令行启动（挨个启动）

![image-20211129225007154](MarkDownImages/06_kafka入门_安装&启动&关闭.assets/image-20211129225007154.png)



脚本启动&关闭

```shell
#!/bin/bash

case $1 in
"start"){
	for i in hadoo102 hadoo103 hadoo104
	do 
		echo "********** $i start **********"
		ssh $i "/opt/module/kafka/bin/kafka-server-start.sh -daemon /opt/module/kafka/config/server.properties"
	done
};;

"stop"){
	for i in hadoo102 hadoo103 hadoo104
	do 
		echo "********** $i stop **********"
		ssh $i "/opt/module/kafka/bin/kafka-server-stop.sh"
	done
};;
esac
```





