# 动效性能与手势（emilkowalski）

上游：https://github.com/emilkowalski/skills —— `skills/animation-performance`、
`review-animations/STANDARDS.md`、`gestures`、`performance-cheatsheet.md`
作者：Emil Kowalski · 许可以原仓库为准
用途：动效"卡、抖、掉帧"时的诊断表，以及手势交互的硬规则。

## 何时读

- 动画掉帧、抖动、只在高负载时卡；
- React/Vue 里动画写进了 state；
- 拖拽、滑动、下拉刷新这类手势要做得"跟手"。

## 症状 → 解法

| 症状 | 解法 |
| --- | --- |
| 动画卡顿 | 只动 `transform` / `opacity`，不动 `width`/`height`/`top`/`margin` |
| 阴影动画抖 | 用 `filter: drop-shadow()`，不要动 `box-shadow` |
| 只在导航/加载时卡 | 把动画移到 CSS 或 WAAPI，让它跑在主线程之外 |
| Motion 的 `x`/`y` 掉帧 | 升级到支持合成层的版本，或直接动完整 `transform` 字符串 |
| 手写 React 动画掉帧 | 写 `ref.current.style`，不要每帧 setState |
| 列表越长拖拽越卡 | 停止动画继承的 CSS 变量，直接设置 `transform` |

## 审查标准（STANDARDS 摘要）

- 频率优先：一天 100+ 次的交互不做动画。
- 每个动效必须能回答"它表达了什么"（层级、因果、连续、状态）。
- 进入 `ease-out`、离开更快；持续运动才用 `linear`。
- 时长随距离与体量变化：微交互 120–250ms，页面级 400–900ms。
- 动画必须可被打断、可被跳过；不得排队堆积。
- 不得同时位移 + 缩放 + 旋转 + 变色（一次只做一件事）。
- 默认就有 `prefers-reduced-motion` 分支，而不是后补。

## 手势

- 跟手优先：拖动时元素 1:1 跟随指针，松手才做惯性/吸附。
- 边界回弹（rubber-banding）而非硬停；越界距离要有阻尼。
- 拖动中禁用文本选择、禁用被拖元素的点击；结束再恢复。
- 手势必须有等价替代：点按按钮、键盘快捷键、或明确的入口。
- 滑动删除必须可撤销，或提供二次确认；不能只有手势一种路径。
- 触屏与鼠标分开判断（`pointer` / `hover` 媒体查询），不要用 UA。
- 触控目标 ≥44×44px，间距 ≥8px，`touch-action: manipulation`。

## 与本研究的关系

主文件第 5 节的四条红线来自这里；`motion.md` 提供落地的技术栈建议。
