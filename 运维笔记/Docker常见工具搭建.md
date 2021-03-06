## Docker常见工具搭建

##### 安装Docker

```
https://cloud.tencent.com/developer/article/1701451
```



##### Docker安装wordPress

```bash
docker run -d --name wordpress \
  -e TZ="Asia/Shanghai" \
  -e WORDPRESS_DB_HOST=127.0.0.1:3306 \
  -e WORDPRESS_DB_USER=root \
  -e WORDPRESS_DB_PASSWORD=password \
  -e WORDPRESS_DB_NAME=wordpress \        
  -p 1080:80 \
  --restart=always \
  wordpress
  
  docker run -d --name wordpress -e TZ="Asia/Shanghai" -e WORDPRESS_DB_HOST=203.189.199.140:3306 -e WORDPRESS_DB_USER=root -e WORDPRESS_DB_PASSWORD=bibilili4455 -e WORDPRESS_DB_NAME=wordpress -p 9002:80 --restart=always wordpress
```

##### Docker安装Nginx

```
https://blog.csdn.net/BThinker/article/details/123507820
```

##### Docker安装mysql

```
docker run -itd --name mysql-test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=bibilili4455 mysql
```

##### Docker安装gitlab

```
docker run -d  -p 7001:443 -p 900:80 -p 222:22 --name gitlab --restart always -v /home/gitlab/config:/etc/gitlab -v /home/gitlab/logs:/var/log/gitlab -v /home/gitlab/data:/var/opt/gitlab gitlab/gitlab-ce
# -d：后台运行
# -p：将容器内部端口向外映射
# --name：命名容器名称
# -v：将容器内数据文件夹或者日志、配置等文件夹挂载到宿主机指定目录

```

##### Docker安装RocketMQ

```
docker run -d -p 9876:9876 --name rmqserver foxiswho/rocketmq:server-4.7.0
https://zhuanlan.zhihu.com/p/342022297
```



##### Docker安装minio文件服务器

```
docker run --name minio -p 9000:9000 -p 9999:9999 -d --restart=always -e "MINIO_ROOT_USER=admin" -e "MINIO_ROOT_PASSWORD=admin123" -v /home/minio/data:/data -v /home/minio/config:/root/.minio minio/minio server /data --console-address '0.0.0.0:9999'
```

##### Docker安装nacos

```bash
docker run --env MODE=standalone --name mynacos -d -p 8848:8848 -p 9849:9849 -p 9848:9848  docker.io/nacos/nacos-server
```

