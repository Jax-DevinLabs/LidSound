<div align="center">

# ⚡ LidSound

**合上笔记本再打开的那一刻，应该有一声属于自己的声音。**

[![platform](https://img.shields.io/badge/platform-Windows%2010%20%2B-lightgrey.svg)]()
[![version](https://img.shields.io/badge/version-0.1.1-blue.svg)](https://github.com/Jax-DevinLabs/LidSound/releases)
[![license](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![offline](https://img.shields.io/badge/privacy-100%25%20offline-brightgreen.svg)]()

</div>

---

## 这是什么

一个Windows 小工具。**你打开笔记本上盖，它播一声你选的音效。**

就这样。没有账号、没有云同步、没有学习成本。装好即用。

<div align="center">

| 你做的事 | 发生什么 |
|---|---|
| 打开笔记本上盖 | 🔊 播一声你选的音效 |

</div>

---

## ⬇️ 下载

**Windows 10 1809+ / Windows 11 · 64 位 · 免费**

<div align="center">

### [**📥 点这里下载 v0.1.2**](https://github.com/Jax-DevinLabs/LidSound/releases/latest)

</div>

| 文件 | 大小 | 说明 |
|---|---|---|
| **`LidSound-Setup.exe`** | 68 MB | **推荐。** 双击安装，自动更新，开始菜单有快捷方式 |
| `LidSound-Portable.zip` | 66 MB | 免安装版，解压双击即用，不写注册表 |

**不用另外装任何东西** —— .NET 运行环境已经打包进去了。

> **⚠️ 可能会看到「Windows 保护了你的电脑」**
>
> 这是因为 LidSound 还没有购买代码签名证书（一张证书约 $70/年）。
>
> 点 **「更多信息」→「仍要运行」** 就能正常安装。
>
> 随着干净安装次数累积，Windows 的警告会自动消失。

---

## 🎧 内置 3 段音效

| 音效 | 听起来像 |
|---|---|
| **机械键盘**（默认） | 一声脆响，带一点弹簧回弹的余韵 |
| **开罐气泡** | 低沉的"噗"，然后一串上浮的气泡 |
| **翻书** | 纸张摩擦的沙沙声 |

全部由程序合成，**不含任何商业音乐或第三方素材**。

---

## ✨ 它不做什么

说清楚边界，比罗列功能更有用：

| | 说明 |
|---|---|
| ❌ **开机动画** | 做不到。UEFI 规范只支持单张静态图片，没有音频通道，第三方厂商做不了 |
| ❌ **合盖时响** | 只在你**打开**上盖时触发。合盖时笔记本可能已进入待机，来不及播 |
| ❌ **敲击音效** | 绝大多数笔记本没有加速度计，只能靠麦克风识别，误触发率高，暂不做 |
| ❌ **动态壁纸** | 改桌面权限复杂、失败率高，不适合放进第一个版本 |
| ❌ **联网 / 账号** | 完全离线。不收集任何数据，不需要注册 |

**CPU 占用可忽略** —— 它只在开盖那一瞬间动作，不像动态壁纸那样持续渲染。

---

## ❓ 常见问题

**Q：我的笔记本支持吗？**
A：绝大多数笔记本都支持。软件用的是 Windows 官方的开盖通知接口，**不装驱动、不要管理员权限**。

极少数机型（部分台式机、一体机、改装机）的固件不上报开盖状态，这时该功能会**静默禁用**，其他一切正常。

想确认？**托盘图标右键 → 「打开日志目录」**，日志就在里面，
里面会写「开盖监听已启动」或「开盖监听不可用」。

<details>
<summary>不想点菜单？日志路径在这里</summary>

| 安装方式 | 日志路径 |
|---|---|
| 安装版 | `%LOCALAPPDATA%\com.jaxdevinlabs.lidsound\current\logs\lidsound.log` |
| 免安装版 | `<你解压的目录>\logs\lidsound.log` |

按 `Win + R` 粘贴路径回车即可打开。
</details>

**Q：会有延迟吗？**
A：约 100ms。这是 Windows 音频设备本身的启动开销，压不下去。这是**用延迟换可靠性** —— 宁可晚 100ms 响，也不要漏播或卡顿。

**Q：占多少资源？**
A：约 260 MB 常驻内存（里面打包了完整的 .NET 运行时）。CPU 在空闲时几乎不占用。

**Q：会不会自动更新？**
A：安装版会。后台静默检查，下载完下次启动生效。不弹窗、不打扰。

> ⚠️ **更新一直失败？** 大概率是你系统里配了个失效的代理
> （VPN 客户端退出后残留的那种）。自动更新要走网络，
> 代理不通就静默失败——不报错、不提示，只是永远更新不到。
> 检查方法：设置 → 网络和 Internet → 代理 → 关掉「使用代理服务器」，
> 或者换一个能用的代理再试。这个问题跟版本无关，任何版本都一样。

**Q：会不会上传我的数据？**
A：不会。完全离线运行，无账号、无遥测、无崩溃上报。见[隐私说明](docs/隐私说明.md)。

**Q：怎么换成自己的音效？**
A：见[用户手册 · 换音效](docs/用户手册.md#换成自己的音效)。解压后编辑一个配置文件就行，不用重新安装。

**Q：怎么卸载？**
A：Windows 设置 → 应用 → LidSound → 卸载。或者直接运行安装包选卸载。

---

## 👋 参与

这个项目还很早期，任何反馈都欢迎：

- 🐛 **[提 Issue](https://github.com/Jax-DevinLabs/LidSound/issues)** 报 bug
  > 报「开盖无声」时，**请附上笔记本型号 + `lidsound.log` 里的相关内容**。
  > 开盖检测能否工作完全取决于机器固件，有日志我能直接定位卡在哪一步。
- 💡 **[提 Issue](https://github.com/Jax-DevinLabs/LidSound/issues)** 提想法
- ⭐ **Star 一下**，让更多需要的人看到它

---

## 📄 许可

[MIT](LICENSE) · 源码不开源，但你可以自由使用、修改、二次分发

---

<div align="center">

**Made with care by [Jax Devin Labs](https://github.com/Jax-DevinLabs)**

</div>
