# Splendor 下载与使用指南

Splendor 将 Blender 场景同步到 PICO 头显，用于空间查看和交互。

**完整体验需要同时安装头显 APK 和电脑 Blender 插件。安装包与教程公开下载，无需 GitHub 账号或源码仓库权限。**

## 下载

推荐下载 **[完整体验包 Splendor-1.01-Experience.zip](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.01/Splendor-1.01-Experience.zip)**，解压后包含两个安装包、入门教程和校验信息。

也可以在 [发行下载页](https://github.com/pengfei2028-arch/splendor-downloads/releases/tag/v1.01) 分别下载：

| 必需组件 | 安装位置 | 下载 |
| --- | --- | --- |
| Splendor 1.01 | PICO 头显 | [Splendor-1.01.apk](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.01/Splendor-1.01.apk) |
| MeshSyncBlender 3.21.5 | 电脑的 Blender | [MeshSyncBlender_v3.21.5.zip](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.01/MeshSyncBlender_v3.21.5.zip) |

项目提供者反馈，上述组合已在 **PICO 开发测试设备 + Blender 5.2** 上测试。其他设备和 Blender 版本尚未确认兼容，设备要求请向项目提供者了解。应用与插件使用独立版本号。

## 第一次使用

请阅读 **[安装与首次同步教程](docs/GettingStarted.zh-CN.md)**，其中包含完整安装流程和常见问题。

1. 在头显安装并启动 Splendor，电脑与头显连接到可互通的局域网。
2. 在 Blender 的“偏好设置 → 插件 → 从磁盘安装”中选择插件 ZIP，启用 `Binary-FileStream Protocol (GLB)`。
3. 在 3D 视图按 **N** 打开 **Binary-Sync** 面板，点击 **Scan** 并选择目标头显。
4. 在 Object Mode 下使用简单立方体场景，点击 **Start** 完成首次同步。每次重新打开 `.blend` 文件后需要再次 Start。

## 关于此下载仓库

Splendor 为闭源软件。本仓库用于分发安装包与使用说明，**不包含 Unity 工程源码**；普通体验用户无需安装 Unity 或编译项目。

GitHub 自动生成的 `Source code (zip)` 和 `Source code (tar.gz)` 仅包含本下载仓库的说明文件，不是安装包，也不包含 Unity 工程。体验请下载上方列出的文件。

两个安装包的 SHA-256 见 [SHA256SUMS.txt](Release/SHA256SUMS.txt)，版本与测试来源见 [release-manifest.json](Release/release-manifest.json)。本次整理核对了文件完整性，未另行进行设备运行复测。
