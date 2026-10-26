# Diana ZCode Theme

[在线体验 ZCode 主题](https://diana-launcher-demo.szbluedream01.chatgpt.site/themes?app=zcode) · [启动器演示](https://diana-launcher-demo.szbluedream01.chatgpt.site/)

可切换日间、暗夜与原版参考，查看示例界面。网页不操作本机，演示效果不代表已完成真实挂载。

面向 ZCode 桌面端的嘉然（Diana）日间 / 暗夜视觉蓝图。

> **公开测试版：[`v0.1.0-beta.1`](https://github.com/lanmengSakura/diana-zcode-theme/releases/tag/v0.1.0-beta.1)。** 本仓库 Release 只提供 CSS、配色 token、美术布局契约与目标专用素材；版本限定的旧版入口另见 [Diana Multi-App Launcher RC.7](https://github.com/lanmengSakura/diana-multi-app-launcher/releases/tag/v0.1.0-beta.4-rc.7)，不等于已支持所有 ZCode 版本。

## 2026-10-26：新版兼容记录

已在 **ZCode 3.16.3.8992** 的本机未登录工作区试验原布局，修正装饰容器层级，避免美术覆盖原生输入和弹窗；没有重新设计尺寸、素材或配色。日间、暗夜、跟随原生、撤下和再挂载已检查，但完整退出后普通重开等扩大验收尚未完成。

本次仅同步公开视觉蓝图与 [兼容范围](COMPATIBILITY.md)，不提供新版一键调试适配器。启动器 `main` 新增的登记入口只有在用户本机另行批准、制作和校验适配器后才能使用；保存路径不是授权，旧 RC.7 下载包不会自动取得这些更新。

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

## 为什么没有公开一键挂载器

ZCode 当前没有覆盖完整桌面工作区的稳定第三方主题 API。已验证方案必须先识别精确版本，再通过本地回环调试检查渲染器；适配器、调试参数、进程状态、日志与截图因此不进入公开仓库。这里的蓝图可以复核设计和差异，但不会自行修改 ZCode。

## 验证

```powershell
npm test
```

最后一轮验收范围见 [PRE_RELEASE.md](PRE_RELEASE.md)。代码使用 [MIT License](LICENSE)，角色与派生美术的边界见 [ASSET_LICENSES.md](ASSET_LICENSES.md)。本项目与 ZCode 官方无隶属或背书关系。
