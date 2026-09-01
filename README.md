# Diana ZCode Theme

面向 ZCode 桌面端的嘉然（Diana）日间 / 暗夜视觉蓝图。

> **预发布状态：`0.1.0-rc.1`。** 本仓库公开 CSS、配色 token、美术布局契约与目标专用素材；构建相关的本机挂载器仍留在私有多合一启动器。最后一轮目标版本回归后再创建正式 Release。

## 源码组成

- `visual-blueprint/diana-zcode.css`：当前完整视觉版式、侧栏状态、悬停/选中导轨与响应式约束。
- `visual-blueprint/zcode-tokens.css`：最小化日间/暗夜 token 映射，便于跟踪原生配色变化。
- `visual-blueprint/zcode-artwork-contract.css`：美术容器的 DOM 和层级契约，不覆盖交互控件。
- `assets/`：嘉然、阿草、星星、糖果、棒棒糖、简笔画和顶部线稿。

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
