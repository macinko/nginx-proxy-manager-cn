此Nginx代理管理器是基于[ nginx-proxy-manager](https://github.com/NginxProxyManager/nginx-proxy-manager)的汉化版，有汉化不对的地方，请在issues留言，以助于我改正。更多高级设置请移至原作者：[传送门](https://nginxproxymanager.com/)

## 快速设置

1. 安装 Docker 和 Docker-Compose

- [Docker 安装文档](https://docs.docker.com/install/)
- [Docker-Compose 安装文档](https://docs.docker.com/compose/install/)

2. 创建一个与此类似的 docker-compose.yml 文件:

```yml
version: '3'
services:
  app:
    image: 'codepiee/nginx-proxy-manager-cn:latest'
    restart: unless-stopped
    ports:
      - '80:80'
      - '81:81'
      - '443:443'
    volumes:
      - ./data:/data
      - ./letsencrypt:/etc/letsencrypt
```

3. 通过运行调出你的堆栈

```bash
docker-compose up -d
```

4. 登录到管理 UI

[http://127.0.0.1:81](http://127.0.0.1:81)

默认管理员用户:
```
Email:    admin@example.com
Password: changeme
```

使用此默认用户登录后，您将立即被要求修改您的详细信息并更改密码。
