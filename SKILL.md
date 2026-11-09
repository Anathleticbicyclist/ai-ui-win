---
name: ai-ui-win
description: UI 交互设计与实现总控技能，融合组件级交互规范（60+ 组件最佳实践）、10 类优先级化 UX 质量门禁、Vercel Web 界面审计清单（100+ 条代码级规则）、反模板化艺术方向方法（三个旋钮 / 三种 AI 陈词滥调 / 暗色模式协议 / 重设计协议）、界面手感细节（光学对齐 / 间距节奏 / 阴影圆角 / 字型微调）与沉浸式动效性能标准。当用户要求设计、生成、重构、评审或并排比较任何界面——网页/落地页、SaaS 后台与仪表盘、表单与数据表、移动端 App 界面（Android XML/Compose、iOS、Flutter、React Native）——或要求交互审计、无障碍检查、设计系统与 token、组件库、动效与滚动叙事、多变体方案探索，或说界面"太像 AI 生成的""模板感""不够高级""交互不顺手""帮我看看这个 UI 有什么问题"时使用。
license: MIT
---

# AI UI Win

把界面工作固定成一条流水线，每一步都有可核对的标准，而不是凭感觉调 CSS：

**定模式 → 读 brief → 定方向 → 出 token → 选组件 → 加动效 → 过门禁 → 审计/重设计 → 交付自检**

## 来源与分工

本技能融合 12 个开源项目的**方法与规则**（完整致谢见仓库 `CREDITS.md`）：

| 项目 | 在本技能里承担 |
| --- | --- |
| carmahhawwari/ui-design-brain | 60+ 组件用法、布局惯例、别名映射 → `references/components.md` |
| nextlevelbuilder/ui-ux-pro-max-skill | 10 类 UX 规则的优先级排序 → `references/ux-rules.md` |
| vercel-labs/web-interface-guidelines | 100+ 条代码级审计规则 → `references/web-audit.md` |
| github/awesome-copilot@premium-frontend-ui | 沉浸式动效与编排标准 → `references/motion.md` |
| Leonxlnx/taste-skill | 三旋钮、brief 推断、陈词滥调规避、重设计协议 → `references/art-direction.md` |
| anthropics/skills@frontend-design | token 先行 + 三种 AI 默认长相 → `references/art-direction.md` |
| jakubkrehel/make-interfaces-feel-better | 对齐/间距/阴影/圆角/字型手感 → `references/craft-details.md` |
| pbakaus/impeccable | 四种 surface 模式、craft floor、绝对禁令 → 本文件 + `craft-details.md` |
| emilkowalski/skill | 动效分级与代码级手感 → `motion.md` 第八节 |
| plugin87/ux-ui-agent-skills | WCAG 2.2、DTCG token、客观验收门禁 → 门禁标准对齐 |
| Laith0003/ux-skill | 反 AI 风格规则分类与品牌规范思路 → 反模式黑名单 |
| joinutlope/variate、superdesign-skill、oil-oil/oil-ui、codeswithroh/tastemaker | 多变体探索与参考图收敛 → `references/explore-variants.md` |

不要按来源分段执行；按下面的顺序合成一条路径。

---

## 0. 定 surface 模式

先判断这个界面为谁、为什么而存在（impeccable 的四模式）：

| 模式 | 访客要完成什么 | 设计优先 | 典型 |
| --- | --- | --- | --- |
| Persuade | 决定并行动 | 注意力与说服力，设计即产品 | 落地页、定价页、活动页 |
| Operate | 完成一个任务 | 可扫读、一致、原生预期 | 后台、编辑器、设置 |
| Read | 理解一件事 | 结构与阅读体验 | 文档、文章、帮助中心 |
| Experience | 沉浸在作品里 | 作品先行，界面后退 | 作品集、画廊、展示 |

同一产品不同页面可以是不同模式（工具的官网首页是 Persuade，工具本身是 Operate）。
另叠一层形态：**页面 / 应用界面 / 组件**。组件只服从周边既有设计，不另立方向。

---

## 1. 读 brief（不发明需求）

提取五个字段，能推断就推断，推断不了就写下判断继续：

1. **对象**：是什么产品，服务谁，要让人做成哪一件**事**。
2. **模式与形态**：见第 0 节。
3. **技术栈**：从项目文件判断（`package.json`、`pubspec.yaml`、`build.gradle`、`*.xcodeproj`、`composer.json`）。绝不默认假定。
4. **既有约束**：品牌色、字体、Logo、设计系统、必须保留的路由/表单/数据。
5. **素材现实**：有没有真实图片、产品截图；没有就不要围绕图片做方案。

---

## 2. 定方向：三个旋钮 + 避开默认款

先读 `references/art-direction.md`，并显式声明三个旋钮（默认 `variance 8 / motion 6 / density 4`；后台把 density 提到 7–8、motion 降到 3–4）。

常规方向：Modern SaaS / Apple 级极简 / 企业后台 / 创意作品集 / 数据看板。
沉浸式方向（仅在需要强表现力时）：Editorial Brutalism / Organic Fluidity / Cyber Technical / Cinematic Pacing。

**只选一个方向**，写一句为什么它承载了主体的想法。**不要混搭两个方向。**

三种 AI 默认长相，命中任一就必须改掉至少一个维度（见到了就当反参考）：
米色暖底 + 衬线大字 + 陶土色强调 / 近黑底 + 酸性绿或朱红单点 / 报纸式零圆角密排多栏。

判据：**把配色与版式套到任何同类产品上都成立 → 它就是默认答案。**

---

## 3. Token 先行，再写第一行代码

先用 6 行写下设计计划（详见 `art-direction.md` 第六节）：

```
palette:   ground / ink / accent / surface / 2 个状态色
type:      display + text，最多 5 级字号，展示/正文比 ≥3
layout:    一句话骨架
signature: 唯一记忆点（1 个）
dials:     variance / motion / density
risk:      一个能说出理由的审美冒险
```

自问三句，答不上就重写：① 换成同类产品还成立吗 ② 去掉装饰靠什么撑住 ③ 记忆点是元素还是效果。

暗色模式默认双模式，按 `art-direction.md` 第五节推导（不用纯黑纯白、语义 token、层级关系一致）。

---

## 4. 组件与交互

按需读 `references/components.md`（60 个组件：别名、最佳实践、常见布局）。先按语义映射组件，再套用法：

- 导航 → Header / Navigation / Breadcrumbs / Tabs
- 表单 → Form / Text input / Select / Checkbox / Radio / Button / Datepicker
- 展示 → Table / Card / List / Badge / Avatar
- 反馈 → Alert / Toast / Modal / Spinner / Progress bar / Empty state
- 浮层 → Modal / Drawer / Popover / Tooltip / Dropdown menu

**跨组件硬规则（违反任一条即不合格）**

- 按钮动词开头（"保存更改"而非"提交"），一个区块一个主操作；触控目标 ≥44×44px。
- 弹窗有 X、取消、Esc 三条关闭路径；焦点陷阱在内，关闭后归还；不嵌套弹窗。
- 表单单列、label 在输入上方、blur 行内校验、错误就近；禁止 placeholder 当 label。
- 表格表头吸顶、数字右对齐、可排序列有指示；空状态 = 插画 + 说明 + 主 CTA，措辞不指责用户。
- 加载 >300ms 用骨架屏（形状匹配真实布局），不用无意义转圈。
- 导航主项 5–7 个，移动端底部 tab ≤5，返回可预期，深层内容可直达。
- Toast 4–6s 自动消失且可手动关闭；破坏性操作给撤销。
- 图标统一一套（线性或填充），对齐文字 16–24px；纯图标按钮必须有可访问名称。
- 深浅色两套都要成立，对比度不因主题降级。

细节手感（对齐、间距节奏、阴影分层、同心圆角、字型微调、状态反馈）全部按 `references/craft-details.md` 执行。

---

## 5. 动效层

读 `references/motion.md`。四条不可协商：

- 只动 `transform` 与 `opacity`；动 `width/height/top/margin` 不合格。
- 先定级别（L1 反馈 / L2 过渡 / L3 揭示 / L4 编舞）：应用界面只做到 L2，全页只做一次大编排。
- 进入 ease-out、离开 ease-in 且更快；直接操作用弹簧；禁止 `linear` 与 `transition: all`。
- 所有动效有 `prefers-reduced-motion` 兜底；重动效与自定义光标只在 `hover:hover` 且 `pointer:fine` 下启用。

---

## 6. 质量门禁 1 → 10

先解决高优先级，再谈风格。完整依据见 `references/ux-rules.md`，代码级细则见 `references/web-audit.md`。

| 优先级 | 类别 | 必须做到 | 禁止 |
| --- | --- | --- | --- |
| 1 | 无障碍 | 对比 4.5:1、alt、键盘可达、aria-label、语义元素 | 去掉焦点环、纯图标无标签 |
| 2 | 触控与交互 | 44×44px、间距 ≥8px、有加载反馈、`touch-action: manipulation` | 只靠 hover、状态瞬变 |
| 3 | 性能 | WebP/AVIF、懒加载、显式尺寸（CLS<0.1）、长列表虚拟化 | 布局抖动、渲染中读布局 |
| 4 | 风格一致性 | 匹配模式与品类、统一图标（SVG 不用 emoji） | 扁平与拟物随机混用 |
| 5 | 布局与响应式 | 移动优先断点、安全区 `env(safe-area-inset-*)` | 固定 px 容器、禁缩放 |
| 6 | 字体与色彩 | 正文 16px、行高 1.5、语义 token | 正文 <12px、灰上灰、裸 hex |
| 7 | 动效 | 分级、可打断、减动效兜底 | 全站一个时长、动 width/height |
| 8 | 表单与反馈 | label 可见、错误就近、提交中禁用、离开前提醒 | placeholder 当标签、错误堆顶部 |
| 9 | 导航 | 返回可预期、底部 tab ≤5、URL 反映状态 | 导航过载、行为断裂 |
| 10 | 图表与数据 | 图例、提示、色盲友好、tabular-nums | 只靠颜色区分含义 |

---

## 7. 审计与重设计

**只做审计**（用户说"看看哪里有问题"）：不写代码、不定方向。按 `web-audit.md` 逐条核对，
输出 `file:line - 问题`，按优先级 1→10 排序，最后给"三个最改变观感的改动"。

**重设计**（用户说"重做/换个样子"）：按 `art-direction.md` 第八节协议执行——
记录现状截图 → 先评审 → 保留内容/行为/品牌 → 按"字型→色彩→框架→状态→换模板构件"顺序改 → 前后截图对比。

**方案探索**（方向不确定 / 用户说不出哪里不对）：按 `references/explore-variants.md` 出 2–3 个结构级变体，
同尺寸渲染截图并排，收敛为 1 个主方案 + 1 个备选。

---

## 8. 交付前自检

1. 跑 `references/app-polish.md` 的 Pre-Delivery Checklist + `craft-details.md` 第十节 10 项手感自检。
2. 截图核对 375 / 768 / 1440（原生按 360dp 起）；看截图判断版面，不看代码。
3. 逐项确认：每个区块有标题、无半屏空白、无元素压字、所有可点元素可点、七种状态（hover/focus/active/disabled/loading/empty/error）都实现。
4. 动效逐条对照第 5 节四条红线。
5. 结论只写发现的问题与已改项，不写"整体不错"。

---

## 9. 反模式黑名单

紫白渐变、卡片墙、彩虹徽章、每处都加动画、placeholder 当 label、无解释的禁用按钮、桌面汉堡菜单、自动轮播、正文 <12px、边框与阴影同用、emoji 当图标、弹窗套弹窗、"点击这里"、编造数据、`outline: none` 无替代、`transition: all`、纯黑纯白、`user-scalable=no`、只用颜色表意。

---

## 10. 输出与协作约定

- 先一句话给方向与理由，再给代码/方案；没定方向不要堆组件。
- 只有"品牌资产缺失 / 栈不可探测 / 素材必须由用户提供"才提问，其余写下假设继续。
- 不编造数据、字体许可、图片、客户 logo；缺素材就说明缺什么并给可执行替代（CSS 绘制、占位结构、请用户补图）。
- 重构既有界面时保留技术栈与可用行为，改动按收益排序、小步提交。
- 本技能只给设计与实现判断，不安装依赖、不改系统配置；引入库前先查依赖文件。

---

## references 索引

| 文件 | 何时读 |
| --- | --- |
| `references/components.md` | 具体组件的用法、布局惯例、别名映射 |
| `references/ux-rules.md` | 审计/评审，或需要某类规则的完整判断依据 |
| `references/web-audit.md` | 代码级 Web 审计（100+ 条，`file:line` 输出） |
| `references/craft-details.md` | 打磨手感、对齐/间距/阴影/圆角/字型/状态 |
| `references/art-direction.md` | 定方向、三旋钮、陈词滥调、暗色模式、重设计协议 |
| `references/motion.md` | 动效分级、编排、性能红线、技术栈落地 |
| `references/explore-variants.md` | 多变体探索、参考图品味档案、收敛 |
| `references/app-polish.md` | 原生端精修与交付前自检 |

版本 v2.0 · MIT · 致谢与来源链接见 `CREDITS.md`
