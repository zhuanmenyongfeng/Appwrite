# Proxy Service for Appwrite Functions

一个适配Appwrite Functions的Node.js代理隧道服务，支持多协议节点生成、nezha监控、Telegram推送等功能。

### 1. 下载部署包

从[Releases](../../releases)页面下载最新的`Appwrite-Functions.tar.gz`压缩包。

### 2. 上传到Appwrite

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

### 🔧 基础配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `UUID` | `48345715-9e60-427a-98db-5e616cbba039` | 节点UUID |
| `NAME` | `Appwrite` | 服务名称 |
| `FILE_PATH` | `./.npm` | 文件存储路径 |
| `SUB_PATH` | `sub` | 订阅路径 |
| `PORT` | `3000` | 服务端口 |

### 🌐 网络配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `CFIP` | `cdns.doon.eu.org` | CloudFlare IP |
| `CFPORT` | `443` | CloudFlare 端口 |
| `ARGO_PORT` | `8001` | Argo 隧道端口 |
| `ARGO_DOMAIN` | `` | Argo 隧道域名 |
| `ARGO_AUTH` | (长字符串) | Argo 隧道认证 |

### 🔌 协议端口配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `TUIC_PORT` | (空) | TUIC协议端口 |
| `HY2_PORT` | (空) | Hysteria2协议端口 |
| `REALITY_PORT` | (空) | Reality协议端口 |

### 📊 监控配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `NEZHA_SERVER` | `nezha.ggff.net:8008` | 哪吒监控服务器 |
| `NEZHA_PORT` | (空) | 哪吒监控端口 |
| `NEZHA_KEY` | `nezha123@` | 哪吒监控密钥 |

### 🔗 外部服务配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `UPLOAD_URL` | (空) | 节点上传地址 |
| `PROJECT_URL` | (空) | 项目访问地址 |
| `AUTO_ACCESS` | `false` | 自动访问保活 |

### 📱 Telegram节点推送配置

| 变量名 | 默认值 | 说明 |
|--------|--------|------|
| `CHAT_ID` | (空) | Telegram聊天ID |
| `BOT_TOKEN` | (空) | Telegram机器人Token |

## 📍 API端点

### 📋 订阅地址
```
GET /sub
```
返回base64编码的节点订阅信息

### 💚 健康检查
```
GET /health
```
返回详细的系统状态信息，包括：
- 服务状态
- 上海时间戳
- 内存使用情况
- 系统信息

### 访问示例

```bash
# 健康检查
curl https://your-function-domain.appwrite.run/status

# 获取订阅
curl https://your-function-domain.appwrite.run/${SUB_PATH}
```

## 📄 许可证

MIT License

---

⭐ 如果这个项目对你有帮助，请给个Star！