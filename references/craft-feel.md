# 手感细节（make-interfaces-feel-better）

上游：https://github.com/jakubkrehel/make-interfaces-feel-better（`skills/make-interfaces-feel-better/SKILL.md`）
作者：Jakub Krehel · 许可以原仓库为准
用途：把"看起来还行"推到"看起来专业"的那 1–2px。`craft-details.md` 的中文版，本文补原作者的原始判断。

## 何时读

- 界面功能齐全但显得业余；
- 卡片、圆角、阴影、图标总有点"不对"；
- 需要逐项打磨而不是重做。

## 五条核心原则

1. **同心圆角（Concentric Border Radius）**
   内层圆角 = 外层圆角 − 内边距。外层 16px + padding 12px → 内层 4px。
   圆角不同心时，视觉上会出现"厚薄不均"的边。

2. **光学对齐优先于几何对齐（Optical over Geometric）**
   文字块在容器里通常要下移 1–2px 才显得居中；图标与文字并排按视觉重心对齐，不按外框。
   左右边距必须成对相等；看起来偏时先做光学校正，不要加装饰去平衡。

3. **阴影表达高度，边框表达结构（Shadows for Elevation, Borders for Structure）**
   浮起来的元素用阴影（多层低透明叠加），需要被"框住"的用边框；两者不并用。
   阴影要有偏移与柔和模糊；零偏移的彩色光晕只是装饰。

4. **动画必须可打断（Interruptible Animations）**
   用户中途操作时，动画从当前位置继续或反向，不跳回起点、不排队。
   进入/离开共用一套空间逻辑：元素从哪儿来，就回哪儿去。

5. **克制（Motion Restraint）**
   一屏只做一次有设计的动效；其余用最少的过渡表达状态。

## 分类清单（原文按类分文件）

- **Typography**：长文本换行（`text-wrap: balance/pretty`）、字体平滑、`tabular-nums` 数字对齐。
- **Surfaces**：圆角、光学对齐、阴影、图片描边、可点击热区（hit area 大于视觉尺寸）。
- **Animations**：可打断、进入/离开、图标动画、按下缩放、克制。
- **Icons**：线宽统一、用 `currentColor` 表达状态、线性与填充二选一、尺寸、RTL 镜像。
- **Performance**：transition 只写具体属性、`will-change` 用完即撤。

## 落地检查（10 条）

1. 所有内外圆角同心吗？
2. 文字块视觉居中了吗（而不是数学居中）？
3. 图标与文字是视觉对齐吗？
4. 卡片是否边框与阴影并用？
5. 阴影是否统一光源方向？
6. 装饰性图标是否 `aria-hidden`，按钮图标是否有名称？
7. 数字列是否 `tabular-nums`？
8. 动画是否可被打断、是否有 reduced-motion？
9. `will-change` 是否只在动画期间存在？
10. 可点击区域是否大于等于视觉尺寸（≥44px）？

## 与本研究的关系

`craft-details.md` 是本节的体系化中文重写（含间距节奏、字型微调、状态反馈、绝对禁令），
两者一起用：先用本文的五条原则判断"哪里不对"，再用 craft-details 的清单逐项修。
