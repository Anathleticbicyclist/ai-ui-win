# 动效与设计工程（emilkowalski）

上游：https://github.com/emilkowalski/skills —— `skills/emil-design-eng`、`animate`、
`animation-vocabulary`、`choreograph`、`improve-animations`、`review-animations`、`gestures`
作者：Emil Kowalski（Sonner / Vaul 作者）· 许可以原仓库为准
用途：动效不只是"加个 transition"，而是设计工程的基本功。需要定义动效语义、编排、审查时读。

## 何时读

- 要给一段动效定语义（该动什么、动多少、多久）；
- 多个元素同时入场，需要编排而不是一起淡入；
- 需要审查既有动效是否"廉价"。

## 三条核心哲学

1. **品味是训练出来的，不是天生的**：把每个细节和"更好的版本"比较，形成可复用的判断。
2. **看不见的细节会叠加**：单个 20ms 的差异用户说不出，但十个叠起来就是"这软件很顺/很糙"。
3. **美是杠杆**：同样功能的两个产品，手感更好的那个会被认为更可信。

## 频率表（先问"这个动作一天发生几次"）

| 频率 | 决定 |
| --- | --- |
| 一天 100+ 次（快捷键、命令面板开关） | **完全不做动画** |
| 一天几十次（hover、列表切换） | 删除或大幅削减 |
| 偶尔（弹窗、抽屉、toast） | 标准动画 |
| 罕见/首次（引导、成就） | 可以加惊喜 |

**键盘发起的动作永远不做动画**——它一天重复几百次，动画只会让它变慢。

## 缓动选择

| 场景 | 曲线 |
| --- | --- |
| 进入 / 离开 | `ease-out`（先快，响应感强） |
| 屏幕内移动 / 形变 | `ease-in-out` |
| hover / 颜色变化 | `ease` |
| 持续运动（跑马灯、进度） | `linear` |

离开比进入快约 20%；`ease-in` 用于离开会显得拖沓。

## 编排：先给元素分角色

| 角色 | 是什么 | 处理 |
| --- | --- | --- |
| Lead | 用户必须注意到的那一个（标题、新视图、被操作项） | 先动、动得最多、留在屏幕上 |
| Support | 跟随内容（副标题、CTA、列表其余项） | 跟随，幅度更小、更短 |
| Decoration | 徽章、胶囊、分隔线、背景装饰 | 只淡入，不位移；或者完全不动 |
| Static | 其他一切，含承载动画的容器 | 不动 |

默认让 Lead 与 Support **一起**动（同曲线、同起点、不同幅度），只有需要表达因果时才做先后错开（stagger 60–90ms）。

## 动效词汇（说清你要的是哪一种）

- **Stagger**：多个元素依次入场，形成瀑布。
- **Origin-aware**：从触发它的元素处长出来（弹窗从按钮位置放大，而不是从屏幕中心）。
- **Morph**：一个形状连续变成另一个形状（如灵动岛）。
- **Crossfade**：同一位置的旧内容淡出、新内容淡入。
- **Shared element transition**：元素从一处移动并形变到另一处（位置连续）。
- **Rubber-banding**：拖过边界时的阻力与回弹（iOS 过卷手感）。
- **Interruptible**：用户中途操作时，动画从当前位置继续，不跳回起点。

## Before / After 审查格式（必须用这个格式提改动）

| Before | After | 为什么 |
| --- | --- | --- |
| `transition: all 300ms` | `transition: transform 200ms ease-out` | 明确属性，避免 all |
| `scale(0)` 入场 | `scale(.95)` + `opacity: 0` | 现实里没有东西从"无"出现 |
| 下拉用 `ease-in` | `ease-out` + 自定义曲线 | ease-in 迟钝，ease-out 有即时感 |
| 按钮无 `:active` | `:active { transform: scale(.97) }` | 按下必须有物理反馈 |
| 弹层从中心缩放 | `transform-origin` 指向触发器 | 弹层应从来源长出来 |

## 与本研究的关系

`motion.md` 第八节的分级（L1–L4）与本节互补：分级决定"做不做"，本节决定"怎么做才不廉价"。
性能与手势细节见 `motion-performance.md`。
