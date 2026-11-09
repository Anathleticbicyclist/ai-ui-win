# AI UI Win

一个把"UI 设计与交互"做成固定流水线的 Agent Skill。融合 15 个主流 UI/UX 开源项目的方法与规则，
**每个项目都有独立参考文件**，面向网页、后台、仪表盘、移动端原生界面，覆盖
**设计 → 实现 → 审计 → 重设计 → 多方案探索 → 交付自检**全链路。

> 目标不是"让 AI 画得更好看"，而是**让每次产出都有可核对的判断标准**：方向是选的，不是随机生成的；
> 门禁是逐条过的，不是"整体不错"。

---

## 它解决什么问题

| 常见症状 | 本技能的处理 |
| --- | --- |
| 生成界面像模板、三种长相反复出现 | 三旋钮 + 三种 AI 陈词滥调黑名单 + "换成同类产品还成立就是默认款"判据 |
| 说"不够高级"但说不出哪里不对 | 手感细节 30+ 条（光学对齐、间距节奏、阴影分层、同心圆角、字型微调） |
| 交互不顺手、状态缺失 | 60+ 组件的用法与跨组件硬规则，七种状态必须齐 |
| 审 UI 只能给"建议优化" | 100+ 条代码级审计规则，按 `file:line` 输出问题 |
| 每次改样式都在拆东墙补西墙 | 重设计协议：先评审、保留行为、按收益排序改、前后截图对比 |
| 动效很花但不高级 / 卡顿 | 动效分级 L1–L4 + 只动 transform/opacity + 减动效兜底 |

---

## 结构

```
ai-ui-win/
├── SKILL.md                        # 主文件：流水线 + 触发条件 + references 路由
├── references/                     # 18 个文件，按需加载
│   ├── components.md               # ui-design-brain：60+ 组件用法、布局惯例、别名
│   ├── ux-rules.md                 # ui-ux-pro-max：10 类规则优先级与完整判断依据
│   ├── design-intelligence.md      # ui-ux-pro-max：视觉层级 / 色彩心理 / 交互模式
│   ├── web-audit.md                # Vercel Web Interface Guidelines：100+ 条代码级规则
│   ├── taste-skill.md              # taste-skill：业务 kind → 页面计划、重设计顺序
│   ├── frontend-design.md          # Anthropic：token 先行四要素、三种 AI 默认长相
│   ├── surface-modes.md            # impeccable：四种 surface 模式、craft floor、Refuse
│   ├── craft-feel.md               # make-interfaces-feel-better：圆角/对齐/阴影/可打断
│   ├── craft-details.md            # 手感体系：间距节奏、字型微调、状态、10 项自检
│   ├── motion.md                   # premium-frontend-ui：Awwwards 级编排与性能红线
│   ├── motion-craft.md             # emilkowalski：频率表、缓动、角色编排、动效词汇
│   ├── motion-performance.md       # emilkowalski：掉帧症状表、审查标准、手势
│   ├── tokens-gates.md             # ux-ui-agent-skills：DTCG token、契约、七态、50 门禁
│   ├── brand-profiles.md           # ux-skill：160 套品牌档案、152 条反 AI 规则
│   ├── taste-profile.md            # tastemaker：reference-board / style-lock / 决策日志
│   ├── explore-variants.md         # superdesign / oil-ui / variate：探索与收敛协议
│   ├── art-direction.md            # 三旋钮、陈词滥调、暗色模式、重设计协议
│   └── app-polish.md               # 原生端（iOS/Android）精修与交付前自检
└── CREDITS.md                      # 15 个参考项目、作者与许可
```

`SKILL.md` 是唯一入口，其余文件按需读取（渐进披露），不会一次性塞满上下文。

---

## 安装

### 方式 A：放进 Agent 的 skills 目录（推荐）

不同运行时的 skills 根目录不同，常见位置：

```bash
# Claude Code / 兼容 Agent
git clone https://github.com/Anathleticbicyclist/ai-ui-win.git ~/.claude/skills/ai-ui-win

# 豆包办公 / Agent Mode（路径以本机实际为准）
git clone https://github.com/Anathleticbicyclist/ai-ui-win.git \
  ~/.doubao/agent_mode/workspace/.user_skills/ai-ui-win
```

放好后重启会话或重新扫描 skills，Agent 即可在匹配请求时自动加载。

### 方式 B：手动复制

```bash
mkdir -p <your-skills-dir>/ai-ui-win
cp -r SKILL.md references <your-skills-dir>/ai-ui-win/
```

### 方式 C：只在单个项目里用

在项目根目录创建 `AGENTS.md` / `CLAUDE.md`，加入一行引用：

```markdown
UI 相关任务一律先读 ai-ui-win/SKILL.md 并按其中的流水线执行。
```

---

## 如何调用

**自动触发**：当你说到这些场景时，Agent 会自己匹配并加载（见 `SKILL.md` 的 description）：

- "帮我做一个 SaaS 落地页 / 后台仪表盘 / 设置页"
- "这个界面太像 AI 生成的了，帮我改"
- "审一下这个 UI，有哪些交互和无障碍问题"
- "这个页面不够高级，但我说不上来哪里不对"
- "给我三个不同方向，我选一个"

**显式调用**（最稳）：

```text
用 ai-ui-win 帮我设计一个骑行数据看板的详情页，深色模式为主
用 ai-ui-win 审计 src/components 下的界面，按 file:line 输出问题
用 ai-ui-win 重做这个登录页，保留现有表单字段和后端接口
用 ai-ui-win 出三个结构不同的方案，截图并排给我选
```

**一条请求里说清三件事效果最好**：① 做什么界面 ② 给谁用/要促成什么动作 ③ 技术栈或现有约束。

---

## 典型工作流

```
定 surface 模式  →  读 brief（5 字段）  →  定方向（1 个）+ 三旋钮
      →  token 计划（6 行）  →  组件与交互（hard rules）
      →  动效分级 L1–L4  →  质量门禁 1→10
      →  审计 / 重设计 / 变体收敛  →  交付前自检（截图三档宽度）
```

技能会强制在写代码前产出方向与 token；审计类请求只输出问题清单，不动代码。

---

## 适用与不适用

**适用**：Web 页面与应用界面、SaaS 后台、仪表盘、表单与数据表、移动端原生界面（Android XML/Compose、
iOS、Flutter、React Native）、设计系统与 token、组件库、交互动效与滚动叙事、UI 评审。

**不适用**：纯图形设计（海报、Logo、插画——请用图像生成技能）、纯后端逻辑、性能压测、
需要真实素材但素材缺失时的"凭空造图"。

---

## 致谢

本项目的规则与方法整理自下列开源项目，**版权归各原作者**，本项目只做筛选、重写、编排与中文化：

- carmahhawwari/ui-design-brain
- nextlevelbuilder/ui-ux-pro-max-skill
- vercel-labs/web-interface-guidelines · vercel-labs/agent-skills
- github/awesome-copilot（premium-frontend-ui，作者 Utkarsh Patrikar）
- Leonxlnx/taste-skill
- anthropics/skills（frontend-design）
- jakubkrehel/make-interfaces-feel-better
- pbakaus/impeccable（Apache 2.0）
- emilkowalski/skills（animate / choreograph / animation-performance / gestures 等）
- plugin87/ux-ui-agent-skills
- Laith0003/ux-skill
- codeswithroh/tastemaker
- superdesigndev/superdesign-skill
- oil-oil/oil-ui
- Nutlope/variate

每个项目对应哪个参考文件、贡献了什么，见 [CREDITS.md](CREDITS.md)。
若你是原作者并希望调整署名或移除内容，请开 issue，我们会尽快处理。

---

## 许可

本项目自身以 MIT 发布（见 [LICENSE](LICENSE)）。
`references/` 中改编自上游的内容，其版权与许可仍归上游项目所有，商用或再分发前请核对 `CREDITS.md` 中列出的原始许可。
