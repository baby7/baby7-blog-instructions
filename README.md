#  七仔的博客系统安装说明

```
提前说明：
如果是云服务器安装需要开放的端口为80(博客地址)、8888(博客后端地址)
不要开放其余端口，以免服务器遭受攻击!!!
以下操作除了取得基本配置外其他步骤均可自行修改
```

## 通过docker-compose安装

> ### 一、安装Docker客户端

推荐安装1.10.0以上版本的Docker客户端

```
curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun
```

> ### 二、docker镜像加速(选做)

针对Docker客户端版本大于 1.10.0 的用户

可以通过修改daemon配置文件/etc/docker/daemon.json来使用加速器

关于阿里加速地址可以从[这里](https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors)获取

```
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["你自己的阿里加速地址"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
```

> ### 三、安装docker-compose

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

> ### 四、取得基本配置

#### 基本SQL文件

```
wget https://cdn.baby7blog.com/docker/v0.1/sql/blog.sql
```

#### docker-compose配置文件

标准版（二选一）:

```
wget https://cdn.baby7blog.com/docker/v0.1/docker-compose/docker-hub/docker-compose.yml
```

阿里云加速版（二选一）:

```
wget https://cdn.baby7blog.com/docker/v0.1/docker-compose/docker-aliyun/docker-compose.yml
```

> ### 五、启动容器

```
docker-compose up -d
```