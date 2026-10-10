# LidSound

打开笔记本上盖时，播放一段你选好的音效。Windows 桌面小工具，免费、完全离线。

[![platform](https://img.shields.io/badge/platform-Windows%2010%20%2B-lightgrey.svg)]()
[![license](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![offline](https://img.shields.io/badge/privacy-100%25%20offline-brightgreen.svg)]()

---

## 下载

Windows 10 1809+ / Windows 11，64 位。

**[下载最新版](https://github.com/Jax-DevinLabs/LidSound/releases/latest)**

| 文件 | 说明 |
|---|---|
| `LidSound-Setup.exe` | 安装版（推荐）。双击安装，支持自动更新，开始菜单和桌面有快捷方式 |
| `LidSound-Portable.zip` | 免安装版。解压即用，不写注册表 |

.NET 运行时已打包在内，不需要另外安装环境。

> 首次运行可能出现「Windows 保护了你的电脑」提示。原因是项目尚未购买代码签名证书，
> 点「更多信息」→「仍要运行」即可正常安装。干净安装量积累后，这个警告会自动消失。

---

## 功能

- **开盖响一声。** 通过 Windows 官方电源通知接口检测开盖，不装驱动、不需要管理员权限。
- **内置 5 段音效**：konan-hiramekiyin（默认）、蜘蛛侠、best-anime-ever、bye-bye-soundbible、马里奥跳跃，可在应用里试听、切换。
- **换成自己的音频。** 在应用里直接上传，wav / mp3 / flac / ogg / m4a 等常见格式都支持，可以裁剪片段、指定从哪里开始播。
- **常驻后台。** 主窗口收起或关闭后，程序仍在托盘运行，音效照常工作；托盘图标右键「退出」才真正结束。
- **完全离线。** 无账号、无遥测、无崩溃上报。

CPU 占用可忽略——它只在开盖那一瞬间动作，平时什么都不做。

---

## 它不做的事

说清楚边界，比罗列功能有用：

| | 说明 |
|---|---|
| **开机动画** | 做不到。UEFI 只支持单张静态图片，没有音频通道 |
| **合盖时响** | 只在打开上盖时触发。合盖时笔记本通常已进入待机，来不及播 |
| **敲击音效** | 绝大多数笔记本没有加速度计，靠麦克风识别误触发率高，暂不做 |

---

## 常见问题

**Q：我的笔记本支持吗？**

A：绝大多数支持。极少数机型（台式机、部分一体机、改装机）的固件不上报开盖状态，这类机器会退而在系统从睡眠唤醒时播放。

想确认的话，托盘图标右键 →「打开日志目录」，日志里会写「开盖监听已启动」或「开盖监听不可用」。安装版的日志路径：
`%LOCALAPPDATA%\com.jaxdevinlabs.lidsound\current\logs\lidsound.log`

**Q：会有延迟吗？**

A：约 100ms，这是 Windows 音频设备本身的启动开销。宁可晚 100ms 响，也不漏播。

**Q：占多少资源？**

A：约 260 MB 常驻内存（里面打包了完整的 .NET 运行时），CPU 空闲时几乎不占用。

**Q：会自动更新吗？**

A：安装版会。后台静默检查，下载完下次启动生效。

> 一直更新不到？大概率是系统里残留了失效代理（VPN 客户端退出后常见）。
> 检查方法：设置 → 网络和 Internet → 代理 → 关掉「使用代理服务器」，或者换一个能用的代理。

**Q：怎么换成自己的音效？**

A：主界面「添加音效」上传音频文件即可，详见[用户手册 · 换成自己的音效](docs/用户手册.md#换成自己的音效)。

**Q：会上传我的数据吗？**

A：不会。完全离线运行，无账号、无遥测、无崩溃上报。见[隐私说明](docs/隐私说明.md)。

**Q：怎么卸载？**

A：Windows 设置 → 应用 → LidSound → 卸载，或直接运行安装包选卸载。

---

## 反馈

这个项目还很早期，欢迎[提 Issue](https://github.com/Jax-DevinLabs/LidSound/issues)。

报「开盖无声」时，请附上笔记本型号和 `lidsound.log` 里的相关内容。开盖检测能否工作取决于机器固件，有日志能直接定位卡在哪一步。

---

## 许可

[MIT](LICENSE) · 源码不开源，但你可以自由使用、修改、二次分发

---

[Jax Devin Labs](https://github.com/Jax-DevinLabs)
