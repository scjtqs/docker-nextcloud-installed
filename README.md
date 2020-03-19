## 开始使用
> git clone https://github.com/scjtqs/docker-nextcloud-installed.git nextcloud-docker-installed

> cd nextcloud-docker-installed

> docker-compose up -d


## 关闭

> docker-compose down

## docker for win 注意事项

> 需要在nextcloud/config/config.php中增加一个配置项

> `'check_data_directory_permissions' => false,`     #检查数据目录权限

> docker-compose.yml中对应的目录地址，请全部修改为win下对应的本地目录地址

## 一些默认参数

> nextcloud已经安装完成并完成初步配置，默认用户 admin 密码 admin
> 
> 数据库root密码为root
> 
> nginx预制配置文件中的域名需要自行修改，默认为cloud.scjtqs.com
> 
> docker-compose,yml 中的域名为cloud.scjtqs.com ，需要自行修改。
> 
> nginx 的反向代理，预制了nextcloud和onlyoffice 的，https的部分需要自行放入证书并修改对应的域名。
> 
> 默认的文件路径为 nextcloud-data，可以自行移动到其他位置，并修改docker-compose.yml中的配置。或者ln -s 软连接过来。

# 升级流程
> docker-compose 升级镜像真tm方便：
>
> 1、docker-compose down 停止服务
>
> 2、docker-compose pull 更新image
>
> 3、docker-compose up -d 启动服务
>
> 3、docker image prune 删除旧的镜像
