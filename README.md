## 环境准备
这个OJ安装程序是把QDUOJ的安装程序作了修改备份上来的。万分感谢QDUOJ！
如果大家想使用请去原版git：QDUOJ的地址在这里: [https://github.com/QingdaoU/OnlineJudgeDeploy/tree/2.0](https://github.com/QingdaoU/OnlineJudgeDeploy/tree/2.0)
我用的Ubuntu14的环境
这里的docker-compose.yml我做了修改，把前端部分改成了我的阿里云容器仓库地址。
### Linux 环境
如何部署参照教程：[https://my.oschina.net/finchxu/blog/1927273](https://my.oschina.net/finchxu/blog/1927273)
## 开始安装

1. 请选择磁盘空间富余的位置，运行下面的命令

    ```bash
    git clone https://github.com/finch-xu/hebauojdeploy.git && cd OnlineJudgeDeploy
    ```

2. 启动服务

    ```bash
    docker-compose up -d
    ```

    > 对于非root用户，请用 `sudo -E docker-compose up -d`，否则不会传递当前的 `$PWD` 环境变量。

根据网速情况，大约5到30分钟就可以自动搭建完成，全程无需人工干预。

等命令执行完成，然后运行 `docker ps -a`，当看到所有的容器的状态没有 `unhealthy` 或 `Exited (x) xxx` 就代表 OJ 已经启动成功。

## 尽情享用吧

通过浏览器访问服务器的 HTTP 80 端口或者 HTTPS 443 端口，就可以开始使用了。后台管理路径为`/admin`, 安装过程中自动添加的超级管理员用户名为 `root`，密码为 `rootroot`， **请务必及时修改密码**。

不要忘记阅读文档 http://docs.onlinejudge.me/

## 定制

我写的定制前端的笔记在这里：[https://my.oschina.net/finchxu/blog/1930017](https://my.oschina.net/finchxu/blog/1930017)
和这个：[https://my.oschina.net/finchxu/blog/1930191](https://my.oschina.net/finchxu/blog/1930191)

2.0 版将一些常用设置放到了后台管理中，您可以直接登录管理后台对系统进行配置，而无需进行代码改动。

若需要对系统进行修改或二次开发，请参照各模块的**README**，修改完成后需自行构建Docker镜像并修改`docker-compose.yml`

## 遇到了问题？

请参照: [http://docs.onlinejudge.me/](http://docs.onlinejudge.me/#/onlinejudge/faq) ，如有其他问题请入群讨论或提issue。
