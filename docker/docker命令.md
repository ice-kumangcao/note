[TOC]

### docker命令

```shell
# 启动/停止/移除 容器
docker start/stop/rm 容器名
# 新建容器
docker run -dit --name=mysql  -p 33061:3306 -e MYSQL_ROOT_PASSWOR=123456 mysql
# 移除镜像
docker rmi mysql
# 删除<none> 容器
docker rmi $(docker images | grep "none" | awk '{print $3}')
# 清除没有被使用的镜像文件
docker image prune
# docker 复制
docker cp mysql:/root/my.cnf ./my.cnf
# docker 运行dockerfile  mysql.df为dockerfile文件 最后的点为在路径为当前路径
docker build -f mysql.df  -t ice/mysql:5.0.96 .
```

### [docker file指令](https://www.cnblogs.com/linjiqin/p/8735230.html)

1. FROM 基础镜像
2. MAINTAINER 作者信息
3. RUN 运行的命令
4. EXPOSE 暴露的端口
5. WORKDIR 终端进入的工作目录
6. ENV 环境变量
7. ADD 将宿主机的文件拷贝到镜像中
8. ENTRYPOINT 生成容器时运行的命令

