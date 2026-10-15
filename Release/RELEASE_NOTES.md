# Splendor 1.01 完整体验

**完整体验需要两个组件：PICO 头显端 APK + 电脑 Blender 插件，两项都要安装。** 普通体验用户无需 Unity 或源码构建。

推荐下载 **[Splendor-1.01-Experience.zip](https://github.com/pengfei2028-arch/splendor-downloads/releases/download/v1.01/Splendor-1.01-Experience.zip)**，解压后包含两个安装包、入门教程、校验值和版本清单。也可以在本页 Assets 中分别下载：

| 文件 | 用途 |
| --- | --- |
| `Splendor-1.01.apk` | 安装到 PICO 头显 |
| `MeshSyncBlender_v3.21.5.zip` | 在电脑的 Blender 中通过“从磁盘安装”添加并启用 |
| `GettingStarted.zh-CN.md` | 安装与第一次同步的基础教程 |
| `SHA256SUMS.txt` / `release-manifest.json` | 两个安装包的校验信息 |

首次使用请阅读 **[安装与首次同步教程](https://github.com/pengfei2028-arch/splendor-downloads/blob/main/docs/GettingStarted.zh-CN.md)**。主要步骤：安装两个组件 → 打开 Blender 的 `N → Binary-Sync` 面板 → 扫描并选择头显 → 点击 `Start`。重新打开 `.blend` 文件后，需要再次 Start。

## 测试组合

项目提供者反馈，本组安装包已在 **PICO 开发测试设备 + Blender 5.2** 上测试。其他设备和 Blender 版本尚未确认兼容。设备具体要求请向项目提供者了解。

- APK 内嵌版本：**1.01**；Android versionCode：1；包名：`com.MRX2.Splendor`；架构：`arm64-v8a`。
- Blender 插件版本：**3.21.5**；启用后的显示名称：`Binary-FileStream Protocol (GLB)`。
- 应用和插件使用独立版本号。

## 本次整理

本公开下载页提供 APK、Blender 插件、完整体验 ZIP 与入门教程。APK 内嵌版本为 1.01，插件版本为 3.21.5。

本次整理已核对文件完整性、版本信息及插件源码，未另行进行设备运行复测。APK 使用 Android Debug 签名，APK v2 签名验证通过；尚未建立既有 APK 与源码快照的可复现构建对应关系。

安装包与教程公开下载，无需 GitHub 账号或源码仓库访问权限。本下载仓库不包含 Unity 工程源码。
