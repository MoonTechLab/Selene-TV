# Selene-TV

<div align="center">
  <img src="banner.png" alt="Selene-TV" width="440">
</div>

> 📺 **Selene-TV** 是以 [MoonTV](https://github.com/MoonTechLab/LunaTV) / [Helios](https://github.com/MoonTechLab/Helios) 为后端的 **Android TV（Leanback）客户端**，在保证原汁原味的同时，针对大屏与遥控器操作做了沉浸式重构。它基于 **Kotlin + Jetpack Compose for TV** 构建，采用 **ExoPlayer (Media3) / mpv** 双内核播放，内置手机扫码遥控，并支持多平台弹幕聚合。

<div align="center">

![Kotlin](https://img.shields.io/badge/Kotlin-2.2-7F52FF?logo=kotlin&logoColor=white)
![Compose for TV](https://img.shields.io/badge/Compose%20for%20TV-Material3-4285F4?logo=jetpackcompose&logoColor=white)
![Android TV](https://img.shields.io/badge/Android%20TV-6.0+(API_23)-3DDC84?logo=androidtv&logoColor=white)
![Media3](https://img.shields.io/badge/Player-ExoPlayer%20%2B%20mpv-FF5722)
![Leanback](https://img.shields.io/badge/Input-D--pad%20Only-555555)

</div>

<details>
  <summary>点击查看应用截图</summary>
  <br>
  <img src="screenshot/04_detail.png" alt="详情页 Hero">
  <img src="screenshot/01_home.png" alt="首页" width="48%">
  <img src="screenshot/02_movies.png" alt="电影分类" width="48%">
  <img src="screenshot/03_anime.png" alt="动漫每日放送" width="48%">
  <img src="screenshot/05_live.png" alt="直播" width="48%">
  <img src="screenshot/06_player.png" alt="播放器" width="48%">
  <img src="screenshot/07_player_sources.png" alt="播放中详情与换源" width="48%">
  <img src="screenshot/08_live_play.png" alt="直播播放" width="48%">
  <img src="screenshot/09_live_channels.png" alt="直播频道选择" width="48%">
</details>

### 请不要在 B站、小红书、微信公众号、抖音、今日头条或其他中国大陆社交平台发布视频或文章宣传本项目，不授权任何"科技周刊/月刊"类项目或站点收录本项目。

---

## ✨ 功能特性

### 🎯 核心功能
- **多源聚合搜索** —— 多个视频源并发聚合，快速定位想看的内容
- **测速优选** —— 一键为各播放源并发测速，按画质 + 速度实时重排，快速选中最流畅的源
- **多平台弹幕** —— 自动匹配当前剧集弹幕，聚合哔哩哔哩 / 腾讯视频 / 爱奇艺 / 优酷 / 芒果TV / 乐视，并自动选用弹幕最多的来源；播放器内可切换来源、调整显示区域 / 不透明度 / 速度 / 字号 / 密度，支持「关闭 / 手动 / 自动」三种模式
- **分类浏览** —— 电影、剧集、动漫、综艺、直播，分类与地区筛选一应俱全
- **动漫每日放送** —— Bangumi 风格的番剧周表，按星期追番
- **继续观看 / 我的收藏** —— 自动记录播放进度断点续播，卡片长按管理
- **直播频道** —— 央视、卫视、地方、赛事等分类直播
- **手机扫码遥控** —— 内置 Web 服务器，手机扫码即可当遥控器与输入法
- **灵活的使用方式** —— 既可连接 MoonTV / Helios 后端，也支持轻量的本地使用方式

### 🎨 用户体验
- **影院级详情页** —— Apple TV 式全屏 Hero（接入 TMDB 剧照 / Logo），失败自动回退
- **播放增强** —— 片头 / 片尾一键跳过（主要覆盖英美剧与番剧）、0.5×–2.0× 倍速、画面比例切换
- **深色沉浸 UI** —— 纯深色、内容优先的设计，玻璃拟态与柔和聚焦动效
- **D-pad 原生导航** —— 完全为遥控器设计，聚焦清晰、滚动流畅
- **1080p 设计基准** —— 自动适配 4K，dp 尺寸一套到底

### 🔧 技术特性
- **双内核播放** —— ExoPlayer (Media3) 与 mpv 可按需切换，HLS / MP4 原生支持、自适应码率、自动判别格式，疑难片源也能流畅播放
- **应用内更新** —— 启动自动检查新版本，应用内一键下载安装
- **元数据增强** —— 接入豆瓣 / Bangumi / TMDB，封面、评分、剧照、续作信息
- **智能缓存** —— 豆瓣数据与图片内存 + 磁盘双层缓存
- **自签证书友好** —— 兼容自托管后端常见的明文 HTTP 与自签 TLS

## 📱 支持平台

- **Android TV (Leanback)** —— 最低支持 Android 6.0 (API 23)，targetSdk 36
- 仅支持 **D-pad 遥控器** 操作，无触摸 / 鼠标依赖

## 📥 下载安装

前往 [Releases](https://github.com/MoonTechLab/Selene-TV/releases) 下载对应架构的 APK：

| 安装包 | 架构 | 适用设备 |
|--------|------|----------|
| `SeleneTV-<ver>-arm64-v8a.apk` | **armv8** (arm64-v8a) | 64 位 ARM，主流 Android TV / 电视盒子 |
| `SeleneTV-<ver>-armeabi-v7a.apk` | **armv7a** (armeabi-v7a) | 32 位 ARM，较老设备 |

> 不确定架构时优先选 **arm64-v8a**。可用 `adb install` 或文件管理器侧载安装。
>
> 首次安装后，应用会在启动时自动检查更新，后续可直接在应用内一键下载安装新版本。

## 📖 使用说明

### 首次使用
1. 启动后若未登录，会进入登录页，填写 MoonTV / Helios 后端地址与凭据
2. 登录成功后进入主界面，顶部为分类标签栏
3. 在「设置」中可查看**手机遥控二维码**、配置豆瓣 / TMDB 数据源、清理缓存

### 主要功能
- **首页** —— 继续观看、我的收藏与推荐
- **搜索** —— 多源聚合，支持手机输入法远程输入
- **分类** —— 电影 / 剧集 / 动漫 / 综艺 按筛选浏览，直播按频道分类
- **详情页** —— 查看剧照、简介、选集与播放源，一键播放

## 🏗️ 技术架构

- **Kotlin 2.2** —— 开发语言
- **Jetpack Compose for TV (Material3)** —— 声明式 TV UI 框架
- **ExoPlayer (Media3) / mpv** —— 双播放内核，可按需切换
- **akdanmaku** —— OpenGL 弹幕渲染引擎
- **Ktor (Netty)** —— 内嵌 HTTP 服务器，承载手机遥控
- **Coil** —— 图片加载与缓存（含豆瓣防盗链处理）
- **OkHttp** —— 网络请求（信任自签证书）
- **kotlinx.serialization** —— JSON 解析
- **qrcode-kotlin** —— 遥控二维码生成

## ⚠️ 免责声明

1. **仅供学习交流** —— 本项目仅用于技术学习与交流，不提供任何商业服务。
2. **内容来源** —— 应用聚合的内容来源于第三方平台，我们不对内容的合法性、准确性、完整性或可用性承担任何责任。
3. **版权声明** —— 所有影视内容版权归原作者与版权方所有，请用户自觉遵守相关法律法规，支持正版。
4. **使用风险** —— 用户使用本应用所产生的任何直接或间接损失，开发者不承担任何责任。
5. **合规使用** —— 请在使用过程中遵守当地法律法规，不得用于任何违法用途。

**使用本应用即表示您已阅读并同意上述免责声明。**

## 🙏 致谢

- [MoonTV](https://github.com/MoonTechLab/LunaTV) / [Helios](https://github.com/MoonTechLab/Helios) —— 后端服务支持
- [Selene](https://github.com/MoonTechLab/Selene) —— 同系列移动端 / 桌面端客户端
- [AndroidX Media3](https://github.com/androidx/media) —— 播放器内核
- 所有用户的支持

---

<div align="center">
  <p>如果这个项目对您有帮助，请给个 ⭐️ 支持一下！</p>
</div>

[![Star History Chart](https://star-history.dera.page/svg?repos=MoonTechLab/Selene-TV&type=Date)](https://star-history.dera.page/#MoonTechLab/Selene-TV&type=Date)
