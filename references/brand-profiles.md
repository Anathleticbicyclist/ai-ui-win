# 品牌档案与风格世界（ux-skill / 160 套品牌规范）

上游：https://github.com/Laith0003/ux-skill —— `figma-skill/ux-skill-foundations/SKILL.md`、
`data/brands/*.json`（160 套，含 `_index.json`）、152 条反 AI 风格规则、离线 MCP server
作者：@Laith0003 · 许可以原仓库为准
用途：不确定"该是什么风格"时，从真实的品牌世界里取一个坐标，而不是随机发明。

## 何时读

- 需要为某个行业找"专业基准"，例如律所、金融、酒店、运动品牌；
- 团队争论风格，需要一个可引用的参照系；
- 需要把品牌 DNA 转成 Figma variables / token。

## 一、品牌档案的用法（不要照抄，要取坐标）

仓库为每个品牌提供结构化档案（色彩、字型、间距、圆角、层级、语气）。正确用法：

1. 选 **2–3 个**与你产品"同一世界"的品牌（不是同一行业，而是同一气质），例如做高端骑行装备，
   可参考运动品牌 + 户外装备 + 精密仪器各一个。
2. 抽取的是**决策**：底色明度、强调色占比、字型对比度、圆角语言、密度。
3. **禁像素复制**：不复制布局、不复制 logo、不搬版权图片与文案。
4. 把抽取结果写成 5–8 行 taste profile（见 `taste-profile.md`），作为本次任务的约束。

## 二、152 条规则的反 AI 风格检查

规则集按类别组织（配色、版式、装饰、图形、动效、文案），用途不是"背下来"，而是**当黑名单扫描**：
拿你的产出对照，命中即改。与 `SKILL.md` 第 9 节的黑名单互补——那边是高频项，这里是细项。

## 三、Figma variables → token 的正确姿势

- 每个基础族（color / type / space / layout / radius / border / elevation / motion / imagery）一个 collection。
- `figma-variables.json` 存定义，`figma-variables.js` 写入文件；按名字匹配，二次运行是更新而非重建。
- **primitive 隐藏且不绑定作用域**；role 别名引用 primitive，并携带作用域（填充/文字/描边/间距/圆角）。
- 组件里每个 fill、stroke、文字色、padding、gap、radius 都绑定 role 变量；**不输入契约没有的 hex 或数字**。
- 状态是 variant 属性（Default / Hover / Pressed / Focus / Selected / Disabled），会变化的部件必须有对应 variant。
- 焦点环由系统绘制（`color.focus.ring` + 宽度 + 偏移），画在部件外侧。
- 构建后用 `contracts check` 反向校验，确认没有游离值。

## 四、页面由 section 组成

页面不是"一堆组件堆起来"，而是 section 序列：每节一个主张、一个主角、一个动作。
先排 section 顺序，再决定每节用什么组件。

## 五、离线能力

规则集与品牌数据都在本地，可离线运行（含 MCP server），适合内网或无网络环境。
本技能不调用其服务，只借鉴其数据组织方式与规则分类。

## 与本研究的关系

- `art-direction.md` 负责"定方向"，本文件负责"给方向一个真实世界的坐标"。
- `tokens-gates.md` 是同一套 token 思想的可执行版本。
