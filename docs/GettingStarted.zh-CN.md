# Splendor 1.01 安装与首次同步教程

**完整体验 = PICO 头显上的 Splendor APK + 电脑 Blender 中的 MeshSyncBlender 插件，两项都要安装。** 体验用户无需安装 Unity 或编译源码。

项目提供者反馈已测试的组合：**PICO 开发测试设备 + Blender 5.2 + Splendor 1.01 + MeshSyncBlender 3.21.5**。其他设备和 Blender 版本尚未确认兼容；设备要求请向项目提供者了解。

## 1. 下载两个必需组件

打开 [Splendor 1.01 下载页](https://github.com/pengfei2028-arch/splendor-downloads/releases/tag/v1.01)，推荐下载 `Splendor-1.01-Experience.zip`，解压后按本教程安装：

| 文件 | 用途 |
| --- | --- |
| `Splendor-1.01.apk` | 安装到 PICO 头显 |
| `MeshSyncBlender_v3.21.5.zip` | 安装到电脑上的 Blender，保留这个 ZIP，不必解压 |
| `GettingStarted.zh-CN.md` | 本教程 |
| `SHA256SUMS.txt`、`release-manifest.json` | 两个安装包的校验值及版本记录 |

下载页也提供两个安装包的单独下载。不要把整个 `Splendor-1.01-Experience.zip` 当成 Blender 插件安装。应用版本 1.01 和插件版本 3.21.5 是独立编号。

安装包与教程公开下载，无需 GitHub 账号或源码仓库访问权限。

## 2. 准备头显

1. 按项目提供者给出的设备安装方式，将 `Splendor-1.01.apk` 安装到 PICO 头显。开发测试设备的安装入口以实际设备说明为准。
2. 在头显中启动 Splendor，并保持应用运行。
3. 电脑与头显连接到可相互通信的局域网。记下头显的局域网 IP，后面扫描不到设备时可手动填写。

## 3. 在 Blender 5.2 安装插件

1. 打开 Blender，进入 **编辑（Edit）→ 偏好设置（Preferences）→ 插件（Add-ons）**。
2. 打开插件页右上角菜单，选择 **从磁盘安装（Install from Disk）**。
3. 选择下载的 **`MeshSyncBlender_v3.21.5.zip`**，完成安装。
4. 在插件列表搜索 **`Binary`**，找到 **`Binary-FileStream Protocol (GLB)`** 并勾选启用。安装完成不等于已经启用；这里的显示名称与 ZIP 文件名不同。
5. 回到 Blender 主窗口，把鼠标放在 **3D 视图** 上，按 **N** 打开右侧边栏，选择 **Binary-Sync** 标签。
6. 确认面板标题是 **Binary-Sync v3.21.5**。如果关闭了偏好设置的自动保存，请手动保存偏好设置。

## 4. 完成第一次场景同步

1. 先保存当前文件，用简单的立方体场景测试。切换到 **Object Mode（物体模式）**，先保持“多人评审”关闭。
2. 在 **Binary-Sync** 面板的设备区域点击 **Scan**。出现目标设备后，点击对应设备行，插件会填入其 IP 和端口。
3. 如果没有扫描到设备，手动填写头显的局域网 IP。端口默认是 **8080**，若项目提供者另有配置，以实际配置为准。**`127.0.0.1` 指电脑自身，不能当作头显地址。**
4. 点击 **Start**。这会启动同步，并自动进行第一次完整场景发送；不用先点 Force Sync，也不用先选中所有物体。
5. 在头显中查看是否出现立方体。插件显示“Unity 已连接”表示连接到头显中的应用；这里的 Unity 不要求你在电脑上安装 Unity 编辑器。
6. 在 Blender 中移动、旋转或缩放立方体，观察头显里的变化。先验证这个简单场景，再打开自己的项目。
7. 需要重新发送整个场景时，保持 **Start 已启动 + Object Mode**，再点击 **Force Sync**。结束体验时点击 **Stop**，并退出头显中的应用。

第一次使用先保留高级参数默认值。插件默认开启 XR 回传，头显中的移动、旋转、缩放可能写回 Blender，因此建议使用已保存的测试场景或副本。Stop 只停止 Blender 向头显发送；若要停止头显写回 Blender，可在高级折叠区关闭“XR 回传”。

## 5. 记住这几个操作

| 操作 | 用途 |
| --- | --- |
| Scan | 刷新可发现的设备列表；选择设备后仍需 Start |
| Start | 开始同步，并发起第一次完整场景发送 |
| Stop | 停止 Blender 向头显发送；XR 回传由独立开关控制 |
| Force Sync | 同步启动后，重新发送完整场景；停止状态下不会发送 |
| 自动同步 | 默认开启；位于“高级：已验证的通道与调优参数”折叠区 |

**每次重新打开或切换 `.blend` 文件后，都需要再次点击 Start。** 插件不会自动恢复上一个文件的同步状态。

## 6. 常见问题

| 现象 | 处理方法 |
| --- | --- |
| 安装后找不到 MeshSync 插件 | 在偏好设置的插件列表搜索 `Binary`，启用 `Binary-FileStream Protocol (GLB)` |
| 找不到 Binary-Sync 面板 | 确认插件已启用；鼠标放在 3D 视图上按 N，在右侧边栏找标签 |
| Scan 找不到头显 | 确认头显应用已启动、网络可互通；尝试手动填写头显 IP 和端口 |
| 状态是“未开始同步” | 点击 Start |
| 一直显示“等待 Unity 连接…” | 检查头显应用、IP、端口及局域网是否允许设备互访；如系统拦截，请为 Blender 在可信局域网中授予所需网络访问权限 |
| Force Sync 没有发送 | 确认已经 Start，并返回 Object Mode；停止状态或编辑模式会阻止或延后全量发送 |
| 已连接但没看到模型 | 先用简单立方体排查，保持 Object Mode，启动同步后点 Force Sync |
| 打开另一个文件后不再同步 | 再次点击 Start |
| 修改模型没有自动同步 | 检查高级折叠区的“自动同步”；若面板提示定时器没在跑，点击“补挂定时器” |

仍有异常时，可点击面板底部 **“看到异常？点这里抓现场”** 输出诊断信息，并向项目提供者反馈操作步骤、Blender 版本和面板状态。此按钮不保证自动生成独立的日志文件。

## 测试记录与参考

上述设备与 Blender 5.2 的测试情况由项目提供者反馈。本次发布整理核对了文件完整性、APK 版本信息及插件代码，未另行进行设备运行复测。APK 当前使用 Android Debug 签名。

Blender 安装入口参考官方文档：[Blender 5.2 插件设置](https://docs.blender.org/manual/zh-hans/5.2/editors/preferences/addons.html)、[扩展与从磁盘安装](https://docs.blender.org/manual/zh-hans/5.2/editors/preferences/extensions.html)。面板名称、按钮行为与排错提示依据随包提供的 MeshSyncBlender 3.21.5 源码整理。
