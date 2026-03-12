# anytls-go Docker

为 [anytls-go](https://github.com/anytls/anytls-go) 构建的 Docker 镜像。

## 功能特性

- 自动从 GitHub Releases 获取最新版本
- 基于轻量级 Alpine 镜像
- 包含 `anytls-client` 和 `anytls-server` 两个二进制文件

## 快速开始

### 拉取镜像

```bash
docker pull ghcr.io/anytls/anytls-go-docker:latest
```

### 运行服务

```bash
# 启动 anytls-server
docker run -d --name anytls-server \
  -p 443:443 \
  ghcr.io/anytls/anytls-go-docker:latest \
  anytls-server

# 运行 anytls-client
docker run --rm \
  ghcr.io/anytls/anytls-go-docker:latest \
  anytls-client -h
```

## 本地构建

```bash
docker build -t anytls-go-docker .
```

## CI/CD

- 每天 4:44 UTC 自动构建
- 推送到 main 分支时触发构建
- 镜像签名：使用 cosign

## 版本

- Docker 镜像：[ghcr.io/anytls/anytls-go-docker](https://github.com/anytls/anytls-go-docker/pkgs/container/anytls-go-docker)
- anytls-go：[https://github.com/anytls/anytls-go/releases](https://github.com/anytls/anytls-go/releases)
