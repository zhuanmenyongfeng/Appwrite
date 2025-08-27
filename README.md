# Proxy Service for Appwrite Functions

一个适配Appwrite Functions的Nodejs代理隧道服务，自动生成节点订阅、支持nezha监控、Telegram推送等功能。

### 📱 Telegram群组
  https://t.me/eooceu


## 部署指南

### 1. 下载部署包

从[Releases](../../releases)页面下载最新的`Appwrite-Functions.tar.gz`压缩包。

### 2. 上传压缩包到Appwrite

1. 登录 [Appwrite 控制台](https://cloud.appwrite.io)
2. 进入 Functions 部分
3. 创建新函数或选择现有函数
4. 点击 "Create deployment"
5. 选择 "Manual" 上传方式
6. 上传Appwrite-Functions.tar.gz压缩包
7. 等待构建完成

### 3. 配置环境变量

在Appwrite控制台的函数设置中添加以下环境变量：

## 📋 环境变量配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `UUID` | `48345715-9e60-427a-98db-5e616cbba039` | 节点UUID |
| `NAME` | `Appwrite` | 服务名称 |
| `FILE_PATH` | `./.npm` | 节点存储路径 |
| `SUB_PATH` | `sub` | 订阅路径 |
| `CFIP` | `cf.877774.xyz` | 优选域名或优选ip |
| `CFPORT` | `443` | CloudFlare 端口 |
| `ARGO_PORT` | `8001` | Argo隧道端口,使用token需再cf里设置一致 |
| `ARGO_DOMAIN` |  | Argo 隧道域名,留空即使用临时隧道 |
| `ARGO_AUTH` |  | Argo隧道密钥token或json |
| `NEZHA_SERVER` |  | 哪吒v0: nezha.xxx.com  v1: nezha.xxx.com:8008|
| `NEZHA_PORT` |  | 哪吒v1请留空|
| `NEZHA_KEY` |  | 哪吒监控密钥 |
| `UPLOAD_URL` |  | 节点上传地址 |
| `PROJECT_URL` |  | 项目访问地址 |
| `AUTO_ACCESS` | `false` | 自动访问保活 |
| `CHAT_ID` |  | Telegram聊天ID |
| `BOT_TOKEN` |  | Telegram机器人Token |

### 📋 订阅地址
```
# 获取订阅，${SUB_PATH}为订阅路径，默认为sub
https://your-appwrite-domain/${SUB_PATH}
```
返回base64编码的节点订阅信息

### 💚 健康检查
```
# 健康检查
https://your-appwrite-domain/status
```
返回详细的系统状态信息，包括：
- 服务状态
- 上海时间戳
- 内存使用情况
- 系统信息

---

## 📄 许可证

GPL-3.0

---


⭐ 如果这个项目对你有帮助，请给个Star！


