# docker-composer 脚手架

## 适用框架
    - Laravel
    - Think Php

## 使用前 先使用 lsof -i tcp:port 检查env文件中的端口是否被使用

 ## 目录结构
```
├── data                        数据库数据目录
│   ├── redis                   Redis 数据目录
│   └── mysql                   MySQL8 数据目录
├── nginx                       Nginx 目录
│   └── default.conf            Nginx 默认配置文件 如需修改请自行改动
├── php                         Php dockerfile文件目录
│    └── Dockerfile             Docker 安装各类扩展 以及 两个版本的redis扩展 可供选择         
└── docker-compose.yml          docker-compose.yml文件
```
## 使用方法
 - 创建 docker文件夹 在此文件夹下 `clone` 此项目
 - docker同级目录创建app文件夹 此文件夹存放项目文件
 - 修改`env`文件
 - 执行 `docker-compose build && docker-compose up -d`
 - 执行完毕之后访问`localhost:port` 例如 `localhost:8081` 此端口对应env中的`NGINX_PORT`

 ## 感谢使用