# Diana ZCode Theme

[在线体验 ZCode 主题](https://diana-launcher-demo.szbluedream01.chatgpt.site/themes?app=zcode) · [启动器演示](https://diana-launcher-demo.szbluedream01.chatgpt.site/)

可切换日间、暗夜与原版参考，查看示例界面。网页不操作本机，演示效果不代表已完成真实挂载。

面向 ZCode 桌面端的嘉然（Diana）日间 / 暗夜视觉蓝图。

> **视觉蓝图测试版：[`v0.1.0-beta.1`](https://github.com/lanmengSakura/diana-zcode-theme/releases/tag/v0.1.0-beta.1)。** 本仓库 Release 只提供 CSS、配色 token、美术布局契约与目标专用素材。需要直接挂载，请使用 [Diana Multi-App Launcher RC.10](https://github.com/lanmengSakura/diana-multi-app-launcher/releases/tag/v0.1.0-beta.4-rc.10)：内置 **3.6.5.4145 / 3.16.3.8992** 适配，不代表任意版本都支持。

## 2026-10-26：新版兼容记录

已在 **ZCode 3.16.3.8992** 的本机未登录工作区试验原布局，修正装饰容器层级，避免美术覆盖原生输入和弹窗；没有重新设计尺寸、素材或配色。日间、暗夜、跟随原生、撤下和再挂载已检查，但完整退出后普通重开等扩大验收尚未完成。

**RC.10 交付更新：** 新版独立公开适配组件现由多合一启动器提供。普通用户无需个人 `local-runtime.json` 或作者目录：更新启动器，关联实际 `ZCode.exe`，完整退出 ZCode，再阅读风险提示并主动确认。RC.8/RC.9 只有本机登记入口，不包含此公开组件；旧 EXE 不会自动更新。精确版本、官方签名与程序资源摘要校验仍保留，见 [兼容范围](COMPATIBILITY.md)。

## 源码组成

- `visual-blueprint/diana-zcode.css`：当前完整视觉版式、侧栏状态、悬停/选中导轨与响应式约束。
- `visual-blueprint/zcode-tokens.css`：最小化日间/暗夜 token 映射，便于跟踪原生配色变化。
- `visual-blueprint/zcode-artwork-contract.css`：美术容器的 DOM 和层级契约，不覆盖交互控件。
- `assets/`：嘉然、阿草、星星、糖果、棒棒糖、简笔画和顶部线稿。

完整美术以 `diana-zcode.css` 为准；`zcode-artwork-contract.css` 是最小结构示例，不应与完整样式重复叠加。装饰需挂在已核验、具有定位上下文的主工作区内，工作区形成独立堆叠上下文，装饰不接受点击。

实现者需要为以下 CSS 变量绑定 `assets/` 中的本地 URL：

| CSS 变量 | 仓库素材 |
|---|---|
| `--diana-zcode-image-corner` | `diana-left-top-detailed-corner-mask-v7.png` |
| `--diana-zcode-image-upper` | `diana-line-art-approved-upper.png` |
| `--diana-zcode-image-character-dark` / `--diana-zcode-image-character-light` | `diana-night-v3.png` |
| `--diana-zcode-image-doodle` | `diana-doodle-chalk-v2-approved.png` |
| `--diana-zcode-image-star` | `diana-hand-star-reference-v2.png` |
| `--diana-zcode-image-candy-wrapped` / `--diana-zcode-image-candy-lollipop` | 对应两张糖果素材 |
| `--diana-zcode-image-acao-heart` / `--diana-zcode-image-acao-cheer` | 对应两张阿草素材 |

## 蓝图与公开启动器的区别

本仓库继续只维护视觉蓝图，不自行修改 ZCode。公开挂载组件在 [多合一启动器仓库](https://github.com/lanmengSakura/diana-multi-app-launcher) 维护与打包，不复制作者的本机实验目录、路径、进程状态、登录态或日志。

完整挂载使用用户明确确认后的临时回环调试接口。端口没有身份认证，同机其他进程可能读取界面、执行渲染脚本或截图；撤下皮肤或关闭启动器不等于关闭端口，须完整退出本次 ZCode，再从官方入口普通启动。未知版本拒绝，不修改安装文件，不创建自启或后台 watcher；详见启动器 [安全说明](https://github.com/lanmengSakura/diana-multi-app-launcher/blob/main/SECURITY.md)。

## 验证

```powershell
npm test
```

最后一轮验收范围见 [PRE_RELEASE.md](PRE_RELEASE.md)。代码使用 [MIT License](LICENSE)，角色与派生美术的边界见 [ASSET_LICENSES.md](ASSET_LICENSES.md)。本项目与 ZCode 官方无隶属或背书关系。
