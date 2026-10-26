# 🚀 Domino's Surge Custom Ruleset (个人精细分流规则库)

本项目为自用的 **Surge 规则集（RULE-SET）** 托管仓库，专注于主流流媒体、AI 工具、密码管理、游戏加速及防风控场景的精细化分流。

---

## 📑 规则集清单与订阅地址

所有规则均支持在 Surge 中直接通过 `RULE-SET` 引用，并设置 `update-interval=86400`（每日自动更新）。

| 规则名称 | 规则文件 | 分类 | 说明 | Surge 订阅直链 (Raw) |
| :--- | :--- | :--- | :--- | :--- |
| **1Password** | `1Password.list` | 安全与密码 | 涵盖 1Password 核心服务、区域账户与用户文件 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/1Password.list) |
| **Apple Intelligence** | `AppleIntelligence.list` | AI / 智能 | 苹果 AI 核心服务、私密云端计算 (PCC) 与 Siri | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/AppleIntelligence.list) |
| **Google AI Studio** | `AIStudio.list` | AI / 智能 | Google AI Studio、API 与 RPC 沙箱接口 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/AIStudio.list) |
| **台湾流媒体合集** | `TaiwanMedia.list` | 流媒体 | 巴哈姆特、KKTV、Line TV、MyVideo、B站港澳台等 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/TaiwanMedia.list) |
| **MyVideo** | `MyVideo.list` | 流媒体 | 台湾大哥大旗下串流影音平台及 DRM 鉴权 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/MyVideo.list) |
| **爱奇艺海外版** | `iQIYI_TW.list` | 流媒体 | 爱奇艺国际版 (iq.com) 与台湾节点服务器 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/iQIYI_TW.list) |
| **爱奇艺大陆版直连** | `iQIYI_CN.list` | 直连兜底 | 爱奇艺国内数据分片与静态资源，防止误走代理 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/iQIYI_CN.list) |
| **HBO Max** | `HBOMax_Download.list` | 流媒体 | HBO Max 国际与拉美区会话分发 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/HBOMax_Download.list) |
| **Star+ 鉴权/基础** | `StarPlus_Download.list` | 流媒体 | Star+ 鉴权、登录与基础资源 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/StarPlus_Download.list) |
| **Star+ 核心播放** | `StarPlus_Streaming.list` | 流媒体 | Star+ 视频媒体流（支持单独定向走美区） | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/StarPlus_Streaming.list) |
| **Pluto TV** | `PlutoTV.list` | 流媒体 | 派拉蒙旗下免费电视流媒体服务 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/PlutoTV.list) |
| **主流游戏下载分流** | `GameDownload.list` | 游戏与下载 | Xbox, Epic, Rockstar, GOG, EA, Riot 下载分流 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/GameDownload.list) |
| **Steam 下载加速** | `SteamDownload.list` | 游戏与下载 | Steam 内容分发 CDN 与官方下载 IP 段 | [点击获取直链](https://raw.githubusercontent.com/Domino510/rules/Surge/SteamDownload.list) |

---

## 🛠️ Surge 配置文件引用示例

在你的 Surge 配置文件（`.conf`）的 `[Rule]` 区域添加如下规则：

```ini
[Rule]
# 1Password
RULE-SET,https://raw.githubusercontent.com/Domino510/rules/Surge/1Password.list,1Password,"update-interval=86400"

# Apple Intelligence 专用分流
RULE-SET,https://raw.githubusercontent.com/Domino510/rules/Surge/AppleIntelligence.list,"Apple AI","update-interval=86400"

# Google AI Studio
RULE-SET,https://raw.githubusercontent.com/Domino510/rules/Surge/AIStudio.list,"AI Studio","update-interval=86400"

# 台湾流媒体服务
RULE-SET,https://raw.githubusercontent.com/Domino510/rules/Surge/TaiwanMedia.list,台湾流媒体,"update-interval=86400"
```

---

## 📌 规范化改进说明

1. **命名规范统一**：全库采用标准 PascalCase（大驼峰）与清晰的下划线模块划分，消灭文件名空格（如原 `Hbo MaxDL.list`）及缺少后缀的文件（如原 `iqiyiCN`）。
2. **结构平铺高效**：所有规则集中平铺在仓库根目录，URL 直观明了；旧深层目录（`rule/Surge/Taiwan/`）保留镜像以保证旧设备向后兼容。
3. **Surge 语法严格对齐**：彻底修复 `SteamDownload.list` 等文件中的非标准裸写语法，严格遵循 `DOMAIN-SUFFIX` 与 `IP-CIDR` 规范。
