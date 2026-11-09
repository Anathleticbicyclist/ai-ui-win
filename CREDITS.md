# CREDITS · 参考项目与致谢

AI UI Win 不是从零发明的方法论。它的判断标准来自下面这些开源项目与作者。
本项目的贡献是**筛选、重写、编排、中文化**，不是原创这些规则。

若你是下列项目的作者，希望调整署名方式或要求移除某段改编内容，请开 issue，我们会立即处理。

---

## 一、直接融合（规则已进入 references/）

### 1. ui-design-brain
- 仓库：https://github.com/carmahhawwari/ui-design-brain
- 作者：GitHub @carmahhawwari
- 贡献：60+ 界面组件的用法、别名映射、常见布局与设计系统惯例。
- 落地：`references/components.md`（整份保留）
- 许可：见原仓库 LICENSE。

### 2. ui-ux-pro-max-skill
- 仓库：https://github.com/nextlevelbuilder/ui-ux-pro-max-skill
- 作者：GitHub @nextlevelbuilder
- 贡献：UX 规则的优先级体系（无障碍 → 触控 → 性能 → 风格 → 布局 → 字体色彩 → 动效 → 表单 → 导航 → 图表）、
  设计系统与配色/字体推荐思路、原生端精修清单。
- 落地：`references/ux-rules.md`、`references/app-polish.md`、`SKILL.md` 第 6 节门禁表。

### 3. Web Interface Guidelines（Vercel）
- 规则仓库：https://github.com/vercel-labs/web-interface-guidelines
- 分发仓库：https://github.com/vercel-labs/agent-skills（`web-design-guidelines` skill，作者 Vercel）
- 贡献：100+ 条可代码化核对的界面规则（无障碍、焦点、表单、动效、字体、内容处理、图片、性能、
  导航与状态、触控、安全区、暗色模式、i18n、水合、hover、文案），以及 `file:line` 审计输出格式。
- 落地：`references/web-audit.md`（全文保留 + 中文使用说明）。

### 4. premium-frontend-ui（github/awesome-copilot）
- 仓库：https://github.com/github/awesome-copilot（skill 路径 `.github/skills/premium-frontend-ui`）
- 作者：Utkarsh Patrikar
- 贡献：Awwwards 级页面的结构、入场编排、滚动叙事、字体层级、色彩纪律，以及只动
  `transform` / `opacity` 的性能红线。
- 落地：`references/motion.md`（第一至七节的主体）。

### 5. taste-skill（Leonxlnx/taste-skill v2）
- 仓库：https://github.com/Leonxlnx/taste-skill
- 作者：GitHub @Leonxlnx
- 贡献：三个设计旋钮（布局变化 8 / 动效强度 6 / 信息密度 4）、brief 推断、设计系统映射、
  暗色模式协议、重设计审计流程、交付前 preflight、反模板化审美判据。
- 落地：`references/art-direction.md`、`SKILL.md` 第 2 节的三旋钮。

### 6. frontend-design（anthropics/skills）
- 仓库：https://github.com/anthropics/skills（skill 路径 `skills/frontend-design`）
- 作者：Anthropic
- 贡献：先规划 token 系统再写代码；明确点出当前模型三种最常见的"AI 长相"
  （米色底 + 陶土色、近黑底 + 酸性绿、报纸式排版），以及"去装饰但没补内容"的失败模式。
- 落地：`references/art-direction.md` 第二、六、七节。

### 7. make-interfaces-feel-better
- 仓库：https://github.com/jakubkrehel/make-interfaces-feel-better
- 作者：GitHub @jakubkrehel（Jakub Krehel）
- 贡献：对齐、阴影、间距、圆角、字型这些"手感"细节的专业打磨方法。
- 落地：`references/craft-details.md` 第一至六节。

### 8. impeccable
- 仓库：https://github.com/pbakaus/impeccable
- 作者：GitHub @pbakaus（Paul Bakaus）
- 贡献：Persuade / Operate / Read / Experience 四种 surface 模式；craft floor 与绝对禁令；
  "按交付尺寸看渲染结果"的验证方式；refinement 与 redesign 的边界。
- 落地：`SKILL.md` 第 0 节与第 7 节、`references/craft-details.md` 第九节。
- 许可：Apache 2.0（见原仓库）。

### 9. emilkowalski/skill
- 仓库：https://github.com/emilkowalski/skill
- 作者：GitHub @emilkowalski（Emil Kowalski，Sonner / Vaul 作者）
- 贡献：动效与交互取舍、动效分级、代码级手感与性能纪律。
- 落地：`references/motion.md` 第八节。

### 10. ux-ui-agent-skills
- 仓库：https://github.com/plugin87/ux-ui-agent-skills
- 作者：GitHub @plugin87
- 贡献：DTCG 设计 token、组件覆盖、WCAG 2.2 AA–AAA 对齐、可客观核对的验收门禁思路。
- 落地：`SKILL.md` 第 6 节门禁标准对齐、`references/web-audit.md` 的无障碍规则。

### 11. ux-skill
- 仓库：https://github.com/Laith0003/ux-skill
- 作者：GitHub @Laith0003
- 贡献：大规模反 AI 风格规则集的分类思路、品牌规范结构化方式、离线可运行的检查器理念。
- 落地：`SKILL.md` 第 9 节反模式黑名单、`references/art-direction.md` 第二节。

---

## 二、方法启发（探索与收敛）

### 12. variate
- 仓库：https://github.com/joinutlope/variate
- 作者：GitHub @Nutlope（Hassan El Mghari）
- 贡献：一次生成同一组件的多个设计变体用于对比。
- 落地：`references/explore-variants.md`。

### 13. superdesign-skill
- 仓库：https://github.com/superdesigndev/superdesign-skill
- 作者：GitHub @superdesigndev
- 贡献：先探索多个方向、并排比较、再用真实截图逐步收敛的流程。
- 落地：`references/explore-variants.md`。

### 14. oil-ui
- 仓库：https://github.com/oil-oil/oil-ui
- 作者：GitHub @oil-oil
- 贡献：多样式方向探索与视觉方案对比的组织方式。
- 落地：`references/explore-variants.md`。

### 15. tastemaker
- 仓库：https://github.com/codeswithroh/tastemaker
- 作者：GitHub @codeswithroh
- 贡献：用真实参考图与长期积累的"品味档案"约束产出，而不是每次从零随机生成。
- 落地：`references/explore-variants.md` 第四节「参考图法」。

---

## 三、许可与再分发

- 本项目自身：MIT（见 `LICENSE`）。
- 上游内容：版权归各原作者，许可以各仓库为准。`references/components.md`、`ux-rules.md`、
  `app-polish.md`、`web-audit.md` 保留了较多上游原文结构；若用于商业分发，请先核对对应仓库的 LICENSE
  （已知：impeccable 为 Apache 2.0；其余多为 MIT，以仓库实际声明为准）。
- 若上游许可不允许原文再分发，可将 `references/` 中对应文件替换为指向上游仓库的链接，
  `SKILL.md` 的流水线逻辑仍可独立工作。

## 四、致谢语

感谢以上作者把大量实战经验公开成可被 Agent 使用的方法。这份技能只是把他们的判断标准排成一条
更短、更可执行的路径；真正的功劳属于这些原始作者与社区。
