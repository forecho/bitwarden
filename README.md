# 自建 Bitwarden

## Install

### Install Docker

```shell
sudo curl -sSL https://get.docker.com/ | sh
sudo curl -L https://github.com/docker/compose/releases/download/1.25.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

中国版安装

```shell
sudo curl -sSL https://get.daocloud.io/docker | sh
sudo curl -sSL https://get.daocloud.io/daotools/set_mirror.sh | sh -s http://d52bcda9.m.daocloud.io
sudo curl -L https://get.daocloud.io/docker/compose/releases/download/1.25.4/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

换中国源

```shell
vim /etc/docker/daemon.json
```

添加代码：

```json
{
    "registry-mirrors": [
        "https://dockerhub.azk8s.cn",
        "https://docker.mirrors.ustc.edu.cn"
    ]
}
```

重启服务

```
sudo systemctl daemon-reload && sudo systemctl restart docker
```

### Clone Code

```
git clone https://github.com/forecho/bitwarden-docker.git
cd bitwarden-docker
```


### Config env

```shell
cp .env.example .env
```


### Cmd

```
docker-compose up -d #运行服务
docker-compose down #关闭服务
docker-compose restart #重启服务
```


## 参考

[免费开源的bitwarden_rs自建密码管理系统-安装,使用和备份教程](https://gwliang.com/2020/05/04/bitwarden-install/)