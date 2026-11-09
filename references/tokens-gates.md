# Token 体系与客观门禁（ux-ui-agent-skills）

上游：https://github.com/plugin87/ux-ui-agent-skills —— `.claude/skills/design-tokens`、
`design-doctrine`、`gate`、`a11y-audit`（另有 52 组件、WCAG 2.2 AA–AAA、50 条门禁）
作者：@plugin87 · 许可以原仓库为准
用途：把"好不好看"变成"能不能通过检查"。需要建立 token、写验收门禁时必须读。

## 何时读

- 要建立/迁移设计系统；
- 需要给出"客观验收标准"而不是主观意见；
- 团队要一份能机器校验的 UI 门禁。

## 一、DTCG token：原始值 + 语义角色

- 九个基础族：color、type、space、layout、radius、border、elevation、motion、imagery。
- **原始值（primitives）不直接被用**：隐藏、不绑定作用域；由语义角色（roles）别名引用，并携带作用域
  （填充、文字、描边、间距、圆角、边框宽度）。
- 组件层只绑定角色，**禁止在组件里写字面 hex 或魔法数字**。
- 主题切换只换角色指向的原始值，不换组件结构。

## 二、组件契约

- 每个 fill / stroke / 文字色 / padding / gap / radius 都绑定到角色的变量，不允许出现契约未命名的值。
- 状态是 variant 属性值：**Default / Hover / Pressed / Focus / Selected / Disabled**；
  hover、selected、pressed 会变的部件，必须有对应 variant，而不是靠 CSS 临时改。
- 焦点环由系统统一提供（`color.focus.ring`、宽度、偏移），**画在部件外侧**，不由组件各自实现。
- 组件契约写好后要反向校验：`contracts check <目录> --tokens <token 文件>`，确保没有游离值。

## 三、50 条客观门禁的构成（可直接抄的类别）

1. **可访问性**：文本对比 4.5:1 / 大字 3:1、非文本 3:1、焦点可见、键盘可达、图片 alt、图标按钮标签。
2. **触控**：≥44×44、间距 ≥8、`touch-action`、点击态存在。
3. **Token 覆盖**：组件零裸 hex、零魔法间距；语义色不被品牌色顶替。
4. **状态完备**：hover / focus / active / disabled / loading / error / empty 七态。
5. **移动优先**：移动端为基线，桌面为增强；不横向滚动；安全区处理。
6. **排版**：正文 ≥16px、行长 45–75ch、数字用 tabular-nums。
7. **禁止项**：原生 `<select>`、单边彩色边框、纯黑压纯白、只用颜色表意。

## 四、两条 house rules（原文明确"永不发布"）

- **不要用原生 `<select>`**：它自绘箭头、与设计系统脱节、跨平台不一致。
- **不要只在一边加彩色边框**（卡片、提示、toast、callout）：一边强调是廉价的做法，改用背景色阶或左侧色条 + 完整结构。

## 五、taste preflight（写任何标记前先排掉）

- 三四个同权重的等宽卡片 → **必须有一个主导**。
- 全部居中 → 用真实栅格做非对称。
- 重复"左文右图"行。
- 标题只是加粗正文（展示字号至少 2.5 倍）。
- 每个盒子都加阴影（大多数应该平）。
- `#000` 压 `#fff`（用近黑 + 暖白）。
- 多个强调色（中性色承担重量，强调色 ≤1）。

## 六、验证协议

**跑门禁，不要声称**：每条结论必须能指向一个检查结果（对比度数值、尺寸、token 引用、状态截图）。
无法验证的项写"未验证"，不写"应该没问题"。

## 与本研究的关系

主文件第 6 节的门禁表与本文件一一对应；`web-audit.md` 提供 Web 侧的可执行规则，
本文件提供"系统层"的 token 与契约约束。
