# Splendor 下载与使用指南

Splendor 将 Blender 场景同步到 PICO 头显，用于空间查看和交互。

**完整体验需要同时安装头显 APK 和电脑 Blender 插件。安装包与教程公开下载，无需 GitHub 账号或源码仓库权限。**

## 下载

推荐下载 **[完整体验包 Splendor-1.02-Experience.zip](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.02/Splendor-1.02-Experience.zip)**，解压后包含两个安装包、入门教程和校验信息。

也可以在 [发行下载页](https://github.com/pengfei2028-arch/splendor-downloads/releases/tag/v1.02) 分别下载：

| 必需组件 | 安装位置 | 下载 |
| --- | --- | --- |
| Splendor 1.02 | PICO 头显 | [Splendor-1.02.apk](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.02/Splendor-1.02.apk) |
| Splendor 插件 3.22.0 | 电脑的 Blender | [MeshSyncBlender_v3.22.0.zip](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.02/MeshSyncBlender_v3.22.0.zip) |

**头显上装过 1.01 的，请先卸载再安装 1.02**：两个版本的安装包签名不同，系统不允许直接覆盖。

项目提供者反馈，上述组合已在 **PICO 开发测试设备 + Blender 5.2** 上测试，测试范围见[教程末尾](docs/GettingStarted.zh-CN.md#测试记录与参考)。其他设备和 Blender 版本尚未确认兼容，设备要求请向项目提供者了解。应用与插件使用独立版本号。

上一版 1.01（插件 3.21.5）仍可在 [v1.01 下载页](https://github.com/pengfei2028-arch/splendor-downloads/releases/tag/v1.01) 获取。

## 第一次使用

请阅读 **[安装与首次同步教程](docs/GettingStarted.zh-CN.md)**，其中包含完整安装流程和常见问题。

1. 在头显安装并启动 Splendor，头显和电脑连接同一个 Wi-Fi。
2. 在 Blender 的“偏好设置 → 插件 → 从磁盘安装”中选择插件 ZIP，启用 **Splendor**。
3. 在 3D 视图按 **N** 打开 **Splendor** 面板。头显会自动出现在列表里；只有一台时会自动选中。
4. 在 Object Mode 下使用简单立方体场景，点击 **开始同步** 完成首次同步。每次重新打开 `.blend` 文件后需要再次点击。

## 1.02 有什么变化

- 插件改名为 **Splendor**，面板重新整理：日常只需要“头显”列表和“开始同步”，其余设置收进“更多设置”。面板可切换中文 / English。
- 网络里只有一台头显时自动选中，不用先点设备；头显重启后换了地址也会自动跟上。
- 修复：场景里有 WebP 贴图时头显里不显示模型（插件现在会在发送前把 WebP 转成 JPEG / PNG）。
- 修复：停止同步后，头显里的操作仍会改动 Blender 场景。
- 头显第一次打开时提示安装插件、连接同一个 Wi-Fi。

完整说明见 [发布说明](Release/RELEASE_NOTES.md)。

## 关于此下载仓库

Splendor 为闭源软件。本仓库用于分发安装包与使用说明，**不包含 Unity 工程源码**；普通体验用户无需安装 Unity 或编译项目。

GitHub 自动生成的 `Source code (zip)` 和 `Source code (tar.gz)` 仅包含本下载仓库的说明文件，不是安装包，也不包含 Unity 工程。体验请下载上方列出的文件。

两个安装包的 SHA-256 见 [SHA256SUMS.txt](Release/SHA256SUMS.txt)，版本与测试来源见 [release-manifest.json](Release/release-manifest.json)。
