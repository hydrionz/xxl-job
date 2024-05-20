
进入到`Dockerfile`文件所在目录,使用如下命令构建镜像
```shell
#docker build -t {镜像name:tag}
 docker build -t tiamaes/xxl-job-admin:2.4.1 .
```

构建完成后，使用如下命令导出镜像
```shell
#docker save -o {要导出的镜像文件名} {镜像name:tag}
docker save -o docker-xxl-job-admin-2.4.1.tar tiamaes/xxl-job-admin:2.4.1
```

登录到服务器，将镜像文件上传，使用如下命令导入镜像
```shell
#docker load < {镜像文件名}
docker load --input docker-xxl-job-admin-2.4.1.tar
```

使用docker-compose一键部署，参考 https://github.com/hydrionz/xxl-job-docker