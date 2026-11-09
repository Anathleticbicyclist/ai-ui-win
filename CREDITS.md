# CREDITS · 参考项目与致谢

AI UI Win 不是从零发明的方法论。它的判断标准来自下面这些开源项目与作者。
本项目的贡献是**筛选、重写、编排、中文化**，不是原创这些规则。

15 个项目全部有独立参考文件，不是只在致谢里点名。

若你是下列项目的作者，希望调整署名方式或要求移除某段改编内容，请开 issue，我们会立即处理。

---

## 一、组件与交互规范

### 1. ui-design-brain
- 仓库：https://github.com/carmahhawwari/ui-design-brain
- 作者：GitHub @carmahhawwari
- 贡献：60+ 界面组件的用法、别名映射、常见布局与设计系统惯例。
- 落地：`references/components.md`（整份保留）

### 2. ui-ux-pro-max-skill
- 仓库：https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- 作者：GitHub @nextlevelbuilder
- 贡献：10 类 UX 规则的优先级体系、视觉层级 / 色彩心理 / 交互模式三维度判断、设计系统选择、
  原生端精修清单。
- 落地：`references/ux-rules.md`、`references/design-intelligence.md`、`references/app-polish.md`、
  `SKILL.md` 第 6 节门禁表。

### 3. Web Interface Guidelines（Vercel）
- 规则仓库：https://github.com/vercel-labs/web-interface-guidelines
- 分发仓库：https://github.com/vercel-labs/agent-skills（`web-design-guidelines`，作者 Vercel）
- 贡献：100+ 条可代码化核对的界面规则（无障碍、焦点、表单、动效、字体、内容处理、图片、性能、
  导航与状态、触控、安全区、暗色模式、i18n、水合、hover、文案），以及 `file:line` 审计输出格式。
- 落地：`references/web-audit.md`

---

## 二、艺术方向

### 4. taste-skill（v2.5）
- 仓库：https://github.com/Leonxlnx/taste-skill
- 作者：GitHub @Leonxlnx
- 贡献：业务类型（software / gaming / tech / product / service / place）→ 页面计划的映射；
  三个旋钮（布局变化 8 / 动效强度 6 / 信息密度 4）；设计系统映射；暗色模式协议；重设计审计流程；
  交付前 preflight。
- 落地：`references/taste-skill.md`、`references/art-direction.md`、`SKILL.md` 第 2 节。

### 5. frontend-design（anthropics/skills）
- 仓库：https://github.com/anthropics/skills（`skills/frontend-design`）
- 作者：Anthropic
- 贡献：先规划 token 系统再写代码（color / type / layout / principles 四要素）；
  明确点出三种模型默认长相（米色底 + 陶土色、近黑底 + 酸性绿、报纸式排版）；
  微排版禁忌与"去装饰但没补内容"的失败模式。
- 落地：`references/frontend-design.md`、`references/art-direction.md`。

### 6. impeccable
- 仓库：https://github.com/pbakaus/impeccable
- 作者：GitHub @pbakaus（Paul Bakaus）
- 贡献：Persuade / Operate / Read / Experience 四种 surface 模式；craft floor（对比、层次、间距、
  字型、动效、状态、浏览器表面、文案、覆盖）；Refuse 清单；设计词汇表；
  按交付尺寸看渲染结果的验证方式。
- 落地：`references/surface-modes.md`、`SKILL.md` 第 0 节与第 7 节。
- 许可：Apache 2.0

---

## 三、手感与动效

### 7. make-interfaces-feel-better
- 仓库：https://github.com/jakubkrehel/make-interfaces-feel-better
- 作者：GitHub @jakubkrehel（Jakub Krehel）
- 贡献：同心圆角、光学对齐优先于几何对齐、阴影表达高度/边框表达结构、可打断动画、动效克制；
  以及 typography / surfaces / animations / icons / performance 分类细则。
- 落地：`references/craft-feel.md`、`references/craft-details.md`。

### 8. emilkowalski/skills
- 仓库：https://github.com/emilkowalski/skills（原 `emilkowalski/skill`）
- 作者：GitHub @emilkowalski（Emil Kowalski，Sonner / Vaul 作者）
- 贡献：设计工程三条哲学；动效频率表（100+ 次/天不做动画）；缓动选择；
  Lead / Support / Decoration / Static 编排角色；动效词汇（stagger、origin-aware、morph、crossfade、
  shared element、rubber-banding、interruptible）；Before/After/Why 审查格式；掉帧症状表；手势规则。
- 落地：`references/motion-craft.md`、`references/motion-performance.md`、`references/motion.md` 第八节。

### 9. premium-frontend-ui（github/awesome-copilot）
- 仓库：https://github.com/github/awesome-copilot（`.github/skills/premium-frontend-ui`）
- 作者：Utkarsh Patrikar
- 贡献：Awwwards 级页面的结构、入场编排、滚动叙事、字体层级、色彩纪律，以及只动
  `transform` / `opacity` 的性能红线。
- 落地：`references/motion.md`（第一至七节主体）。

---

## 四、Token、门禁与品牌

### 10. ux-ui-agent-skills
- 仓库：https://github.com/plugin87/ux-ui-agent-skills
- 作者：GitHub @plugin87
- 贡献：DTCG token（primitive 隐藏、role 携带作用域）、组件契约（零裸 hex）、七态 variant、
  焦点环由系统绘制、50 条客观门禁类别、两条 house rules（禁用原生 `<select>`、禁止单边彩色边框）、
  taste preflight、"跑门禁不要声称"的验证协议。
- 落地：`references/tokens-gates.md`、`SKILL.md` 第 6 节。

### 11. ux-skill
- 仓库：https://github.com/Laith0003/ux-skill
- 作者：GitHub @Laith0003
- 贡献：160 套品牌档案（结构化色彩/字型/间距/圆角/语气）、152 条反 AI 风格规则、离线 MCP server、
  Figma variables → token 的构建与反向校验方式、页面由 section 组成。
- 落地：`references/brand-profiles.md`、`SKILL.md` 第 9 节黑名单。

### 12. tastemaker
- 仓库：https://github.com/codeswithroh/tastemaker
- 作者：GitHub @codeswithroh
- 贡献：用真实参考图与长期积累的品味档案约束产出；`reference-board.md` / `style-lock.md` /
  `decisions.log` 三件套的组织方式；"参考决策而非复制像素"的纪律。
- 落地：`references/taste-profile.md`

---

## 五、方案探索与收敛

### 13. superdesign-skill
- 仓库：https://github.com/superdesigndev/superdesign-skill
- 作者：GitHub @superdesigndev
- 贡献：设计前的环境预检、有无代码库的分支处理、先抽取 design-system 再提方向、
  多方向并排比较后用真实截图收敛。
- 落地：`references/explore-variants.md`

### 14. oil-ui
- 仓库：https://github.com/oil-oil/oil-ui
- 作者：GitHub @oil-oil
- 贡献：产品事实清单、每屏一个主角/一个主动作、先画灰度线框再实现、先做代表性页面、
  在目标视口看真实截图评审。
- 落地：`references/explore-variants.md`

### 15. variate
- 仓库：https://github.com/Nutlope/variate
- 作者：GitHub @Nutlope（Hassan El Mghari）
- 贡献：同一组件的多变体并排生成、在浏览器里挑选、以 done / more / vary 三种结果收敛，
  "让用户比较看到的东西，而不是描述想要的东西"。
- 落地：`references/explore-variants.md`

---

## 六、许可与再分发

- 本项目自身：MIT（见 `LICENSE`）。
- 上游内容：版权归各原作者，许可以各仓库为准。`references/components.md`、`ux-rules.md`、
  `app-polish.md`、`web-audit.md` 保留了较多上游原文结构；若用于商业分发，请先核对对应仓库的 LICENSE
  （已知：impeccable 为 Apache 2.0；其余多为 MIT，以仓库实际声明为准）。
- 若上游许可不允许原文再分发，可将 `references/` 中对应文件替换为指向上游仓库的链接，
  `SKILL.md` 的流水线逻辑仍可独立工作。

## 七、致谢语

感谢以上作者把大量实战经验公开成可被 Agent 使用的方法。这份技能只是把他们的判断标准排成一条
更短、更可执行的路径；真正的功劳属于这些原始作者与社区。
