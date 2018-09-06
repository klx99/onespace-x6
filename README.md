# onespace-x6
onespace-x6 archiver

###DittoBox移植步骤：
1. 假设x6的ip为~~192.168.0.99~~，操作时根据实际ip调整。
1. 拷贝DittoBox文件夹到/root目录下，并解压其中的owncloud-10.0.9.zip到/root/DittoBox文件夹，并设置文件夹权限为a+rwx。
2. remount根文件系统目录，$ mount -o remount,rw / 。
3. 将owncloud.conf拷贝到/etc/nginx/文件夹。
4. 创建依赖目录，$ mkdir /var/run/elaoc-agentd。
5. 修改/etc/nginx/nginx.conf，添加一行include owncloud.conf;。
6. 重启nginx，$nginx -s reload。
7. 打开网页http:// ~~192.168.0.99~~:11111 配置owncloud。设置用户名和密码，并等待登录成功。
8. 设置lib路径，$ export LD_LIBRARY_PATH=/root/DittoBox/dittobox/lib。
9. 启动DittoBox Server，$ /root/DittoBox/dittobox/bin/elaoc-agentd。

###DittoBox远程连接步骤：
1. 启动DittoBox Server时，在打印log或elaoc-agentd.log 中获取DittoBox Server的address。
如Address: ~~cedaPVCw8BTMwy81pxXNkBPcHiRyAezmxmGQLWWbxT6APGZFuLre~~
2. 打开浏览器，输入http://api.qrserver.com/v1/create-qr-code/?size=240x240&margin=16&data= ~~cedaPVCw8BTMwy81pxXNkBPcHiRyAezmxmGQLWWbxT6APGZFuLre~~，获取地址二维码。
3. 手机端打开DittoBox App，扫描上面二维码进行连接。
