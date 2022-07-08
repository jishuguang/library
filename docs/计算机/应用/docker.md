# docker

## 1 概述

## 2 安装与配置

### 2.1 配置代理

Docker涉及4种不同场景的代理配置：

* Docker client与Docker daemon之间

通常Docker client与daemon位于同一台主机上，此时无需配置代理。倘若位于不同的主机且需配置代理，可设置如下环境变量：

```shell
export http_proxy=xxx
export https_proxy=xxx
export no_proxy=xxx,xxx
```

* Docker daemon与Internet之间



* Container run-time

* Container build-time

参考资料：
* [Ultimate Guide to Docker HTTP Proxy Configuration](https://elegantinfrastructure.com/docker/ultimate-guide-to-docker-http-proxy-configuration/)
* [Control Docker with systemd: HTTP/HTTPS proxy](https://docs.docker.com/config/daemon/systemd/#httphttps-proxy)

## 3 Dockerfile

## 参考资料

* 官方文档：[https://docs.docker.com/](https://docs.docker.com/)