# 部署文档

本文档详细说明如何在不同环境下部署飞书抖音数据采集工具。

## 目录结构

```
feishu-douyin-tool/
├── frontend/          # 前端 Vue.js 项目
├── backend/           # 后端 Node.js 项目
├── Dockerfile        # Docker 部署配置
└── package.json     # 项目配置文件
```

## 环境要求

- Node.js >= 14.x
- npm >= 6.x
- 支持 HTTPS 的域名（飞书开放平台要求）

## 部署方式

### 1. 本地开发环境部署

1. 克隆项目：
```bash
git clone https://github.com/happyVee/feishu-douyin-tool.git
cd feishu-douyin-tool
```

2. 安装依赖：
```bash
npm install
```

3. 构建前端：
```bash
npm run build
```

4. 启动服务：
```bash
npm start
```

服务将在 http://localhost:4000 启动。

### 2. 使用 Replit 一键部署

1. 访问 Replit 部署链接：https://replit.com/@yib360/feishu-douyin-tool
2. Fork 项目
3. 点击 Run 按钮即可运行

### 3. Docker 部署

1. 构建 Docker 镜像：
```bash
docker build -t feishu-douyin-tool .
```

2. 运行容器：
```bash
docker run -d -p 4000:4000 feishu-douyin-tool
```

## 配置说明

### 飞书多维表格配置

1. 在飞书开放平台创建应用
2. 配置应用基本信息
3. 添加多维表格权限
4. 获取应用凭证

### 抖音配置

1. 登录抖音网页版
2. 获取 Cookie（参考 README.md 中的说明）

## 常见问题

1. 端口被占用
   - 修改 backend/bin/www 文件中的端口号

2. Cookie 失效
   - 重新登录抖音网页版获取新的 Cookie

3. 飞书授权失败
   - 检查应用权限配置
   - 确认重定向 URI 配置正确

## 安全建议

1. 生产环境部署时启用 HTTPS
2. 定期更新依赖包
3. 不要在代码中硬编码敏感信息
4. 使用环境变量管理配置

## 维护和更新

1. 定期检查并更新 npm 包
2. 监控服务器资源使用情况
3. 保持日志记录以便追踪问题

## 技术支持

如遇到问题，可以：
1. 查看项目 README.md
2. 提交 GitHub Issue
3. 联系技术支持团队
