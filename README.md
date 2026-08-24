# MinecraftSniper 博客模板 Pro+

> MinecraftSniper 博客模板的 **Pro 增强版**，在 Pro 版基础上新增 **系统级性能监控（CPU / 磁盘 / 网络）** 及 **SSE 实时数据推送**，为管理员提供全方位的服务器状态洞察。

**基础版链接：** [MinecraftSniper 博客模板](https://gitee.com/Minecraft-Sniper/minecraftsniperblogtemplate)  
**Pro 版链接：** [MinecraftSniper 博客模板 Pro](https://gitee.com/Minecraft-Sniper/minecraftsniperblogtemplatepro)

---

## 📖 项目简介

MinecraftSniper 博客模板 Pro+ 是一个**轻量、安全、可管理**的个人博客系统，基于 Node.js + Express 构建，以 Markdown 文件作为内容源，无数据库依赖，开箱即用。

**Pro+ 版本在 Pro 版基础上新增了：**
- 📊 **系统级性能监控**：实时显示 CPU 使用率、磁盘占用、网络流量
- 🔄 **SSE 实时数据推送**：管理后台可通过 EventSource 长连接获取实时状态更新
- 🖥️ **更全面的仪表盘**：集成 CPU、内存、磁盘、网络、缓存、内容统计、运行时间等 8 项核心指标

（Pro 版原有功能全部保留：私钥认证、独立管理后台、文章/动态 CRUD、缓存可视化配置、HTTPS 自动适配等）

---

## ✨ 功能特性

### 前台博客
- **Markdown 写文章**：在 `content/posts/` 中新建 `.md` 文件即可发布
- **动态发布**：在 `content/moments/` 中新建 `.md` 文件发布短动态
- **热更新**：修改 Markdown 文件后，前端自动刷新（无需重启服务）
- **四页面导航**：主页、文章列表、动态列表、关于我
- **响应式设计**：适配桌面端和移动端
- **视觉风格**：参考 HarmonyOS NEXT，支持液态玻璃质感和沉浸光效

### 后台管理
- **🔐 私钥认证**：RSA 2048 位密钥对登录，无需记忆密码
- **📊 性能监控面板**（新增指标）：
  - **CPU 使用率**：实时百分比 + 系统负载（1/5/15 分钟）
  - **磁盘使用率**：已用/总容量 + 占用百分比（跨平台支持）
  - **网络流量**：实时上下行速率（Mbps），支持 Linux 和 Windows
  - **系统内存**：已用/总量 + 使用百分比
  - **Node 进程内存**：RSS、堆使用/总大小
  - **缓存状态**：当前模式（自动/手动/停用）、缓存数据大小、上限
  - **内容统计**：文章数、动态数、总字数
  - **服务运行时间**：已运行时长 + 启动时间
  - **最近日志**：实时查看 `logs/` 目录的最新日志
- **📝 文章管理**：上传 `.md` 文件、下载文章、删除文章
- **✨ 动态管理**：上传 `.md` 文件、下载动态、删除动态
- **🧠 内存缓存管理**：可视化切换 `auto/true/false` 模式，调整缓存上限
- **⚙️ 系统信息**：Node 版本、运行时长、依赖版本、版权信息
- **🔌 SSE 实时推送**：提供 `/api/admin/status/stream` 端点，支持前端仪表盘实时更新

### 技术特性
- **极低资源占用**：2GB 内存即可运行
- **无数据库**：所有内容以 Markdown 文件存储，复制即备份
- **内存缓存管理**：支持 `auto`（自动）/ `true`（手动）/ `false`（禁用）三种模式
- **定时内存检查**：每 30 秒自动检测内存，紧张时自动降级
- **管理界面HTTPS 自动适配**：证书存在时自动启用 HTTPS，不存在时降级为 HTTP
- **中文文件名支持**：上传中文名的 `.md` 文件无乱码
- **跨平台监控**：CPU / 磁盘 / 网络信息在 Linux 和 Windows 上均可采集（通过系统命令或 API）

---

## 🛠️ 技术栈

| 组件 | 技术 |
| :--- | :--- |
| 服务端 | Node.js + Express |
| 前端 | 原生 HTML/CSS/JavaScript |
| 内容源 | Markdown 文件 |
| 文件上传 | Multer |
| 热更新 | chokidar |
| 认证 | RSA 2048 + JWT |
| 日志 | 控制台 + 按天轮转文件 |
| 系统监控 | Node.js `os` 模块 + 系统命令（`df`, `netstat`, `wmic` 等） |
| 实时推送 | Server-Sent Events (SSE) |

---

## 📁 目录结构

详细的目录结构请查看：[目录结构概览.txt](https://gitee.com/Minecraft-Sniper/minecraftsniperblogtemplatepro/blob/master/%E7%9B%AE%E5%BD%95%E7%BB%93%E6%9E%84%E6%A6%82%E8%A7%88.txt)

---

## ⚠️ 安全提醒

- 管理端口请勿直接暴露至公网，建议通过内网或 VPN 访问。
- 私钥文件请妥善保管，丢失后需验证旧私钥才能重置。
- 生产环境建议启用 HTTPS 并设置 `https.enabled = true`。

---

## 🔗 相关链接

- [基础版](https://gitee.com/Minecraft-Sniper/minecraftsniperblogtemplate)
- [Pro 版](https://gitee.com/Minecraft-Sniper/minecraftsniperblogtemplatepro)
- [Pro+ 版（本仓库）](https://github.com/MinecraftSniper/minecraftsniperblogtemplatepro)

---

## 📄 版权信息

© 林鋆成 All Rights Reserved.  
本软件及所有相关代码、文档、设计均受著作权法保护。未经版权所有者书面授权，不得复制、修改、分发或用于商业用途。