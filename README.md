#  七仔的博客系统安装说明

```
提前说明：
以下操作除了取得基本配置外其他步骤均可自行修改
```

## 通过docker-compose安装

> ### 一、首先安装docker

参考教程安装：

[Ubuntu Docker 安装](https://www.runoob.com/docker/ubuntu-docker-install.html)

[Debian Docker 安装](https://www.runoob.com/docker/debian-docker-install.html)

[CentOS Docker 安装](https://www.runoob.com/docker/centos-docker-install.html)

[Windows Docker 安装](https://www.runoob.com/docker/windows-docker-install.html)

[MacOS Docker 安装](https://www.runoob.com/docker/macos-docker-install.html)

> ### 二、docker镜像加速(选做)

参考教程配置，强烈建议使用阿里镜像源：

[Docker 镜像加速](https://www.runoob.com/docker/docker-mirror-acceleration.html)

> ### 三、然后安装docker-compose

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