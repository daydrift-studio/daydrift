# 《度日：Daydrift》

> **在慢下来的日子里，驻足与漫游。一款以生活切片、街道漫游、日常互动与同游旅人为核心的像素生活模拟游戏。**

---

## 欢迎访问官方站点与生态矩阵

- 🌐 **官方主站**：[daydrift.blym.top](https://daydrift.blym.top)（游戏理念介绍、全平台下载与最新动态）
- 📖 **开发者与玩家文档**：[daydrift-docs.blym.top](https://daydrift-docs.blym.top)（游玩手册、开服运维、三体系 Mod SDK 规范）
- 🛒 **Mod 扩展中心**：[daydrift-mods.blym.top](https://daydrift-mods.blym.top)（官方与社区模组浏览、安全签名校验与下载）
- 🛠️ **模组开发工具包**：[daydrift-mod-sdk](https://github.com/daydrift-studio/daydrift-mod-sdk)（创作者 CLI、类型存根与脚手架模板）

---

## 下载与发行版本 (Releases)

本仓库（`daydrift-studio/daydrift`）是《度日：Daydrift》的**官方公开版本发行、社区更新与工单反馈平台**。

请前往右侧的 **[Releases 页面](https://github.com/daydrift-studio/daydrift/releases)** 下载最新构建产物：

### 1. 全平台客户端矩阵
- **Windows 桌面端**：
  - `Daydrift_v{version}_windows_x64.zip` (适用于 Windows 10/11 64-bit)
  - `Daydrift_v{version}_windows_arm64.zip` (适用于 Windows on ARM 原生设备)
- **Linux 桌面端 / SteamOS**：
  - `Daydrift_v{version}_linux_x64.tar.gz` (适用于 glibc 2.31+ 及 Steam Deck 掌机)
  - `Daydrift_v{version}_linux_arm64.tar.gz` (适用于 64位 ARM Linux 发行版)
- **macOS 桌面端**：
  - `Daydrift_v{version}_macos_universal.dmg` (Apple Silicon M 系列与 Intel x86 原生统一包)
- **Android 移动端**：
  - `Daydrift_v{version}_android.apk` (支持触屏虚拟摇杆与手势操作)

### 2. 跨平台独立无头服务端 (Headless Server)
- `Daydrift_Server_v{version}_linux_x64.zip`
- `Daydrift_Server_v{version}_windows_x64.zip`
- `Daydrift_Server_v{version}_macos_universal.zip`

> 服务端基于 Go 语言构建，免除 GPU 图形渲染驱动，内存占用低于 50MB，开箱即用。

---

## 供应链安全：SHA-256 与 Ed25519 签名验证

每个 Release 版本均附带 `SHA256SUMS`、`release.json`、`latest.json` 以及官方数字签名文件（`*.sig`）。为保障纯净安全，下载后建议验证完整性：

### 1. 校验文件完整性哈希
```bash
# Linux / macOS
sha256sum -c SHA256SUMS

# Windows PowerShell
Get-FileHash -Algorithm SHA256 Daydrift_v*.zip
```

### 2. 校验官方 Ed25519 数字签名
官方发布清单使用离线 Ed25519 私钥签名。可使用 Node.js 或 OpenSSL 配合官方公开公钥（公布于 [daydrift-mods.blym.top/keys](https://daydrift-mods.blym.top/keys)）完成防篡改校验。若清单遭到中间人攻击篡改或安装包被修改单个字节，验签将立即失败。

---

## 基础操作键位速查

| 操作功能 | 键盘 / 鼠标按键 | 手柄按键 | 移动触屏手势 |
| :--- | :--- | :--- | :--- |
| **角色横向移动** | `A` / `D` 或 `←` / `→` | 左摇杆 / 方向键左右 | 屏幕左侧虚拟摇杆 |
| **互动 / 调查物件** | `E` 或 `Space` 或 回车 | `A` (Xbox) / `✕` (PS) | 轻触目标物体上的交互气泡 |
| **快速推进对话** | `Space` / `E` / 鼠标左键 | `A` (Xbox) / `✕` (PS) | 点击对话区域 |
| **呼出聊天输入框** | `T` 或 `/` | 选定后按 `A` | 点击左下方聊天气泡 |
| **同游旅人标牌** | `Tab` | `Y` (Xbox) / `△` (PS) | 点击顶栏旅人信息图标 |
| **性能监控 (F3 面板)** | `F3` | 设置中开启调试面板 | 设置中开启调试浮窗 |
| **系统菜单 / 暂停** | `Esc` | `Start` / `Options` | 点击右上角齿轮图标 |

---

## 模组安装与崩溃自愈保护

- **安装目录**：将下载的 `.ddmod` 文件或解压文件夹放入系统的 `mods/` 目录：
  - Windows: `%APPDATA%/Godot/app_userdata/Daydrift/mods/`
  - Linux: `~/.local/share/godot/app_userdata/Daydrift/mods/`
- **崩溃自愈 (`booting.lock`)**：若第三方模组导致启动崩溃，游戏下次启动自动进入安全恢复模式，暂时隔离异常模组，确保核心存档不受污染。

---

## 问题反馈与技术支持 (Issues)

若在游戏游玩、局域网联机或模组开发中发现异常，欢迎通过 [GitHub Issues](https://github.com/daydrift-studio/daydrift/issues) 提交工单。

提交时建议附带：
1. 客户端操作系统及具体架构版本；
2. 异常复现步骤；
3. 本地日志文件（位于用户数据目录下的 `logs/godot.log`）。

---

## 协议与法律条款

- 原创游戏代码、场景设计、美术与音乐资源知识产权完全保留，遵循 [EULA 最终用户许可协议](https://daydrift.blym.top/legal/eula)。
- 隐私声明：纯本地离线设计，零第三方打点追踪，遵循 [隐私政策](https://daydrift.blym.top/legal/privacy)。
