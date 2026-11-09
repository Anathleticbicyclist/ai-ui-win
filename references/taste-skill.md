# taste-skill v2（反模板化艺术指导）

上游：https://github.com/Leonxlnx/taste-skill（`skills/taste-skill/SKILL.md`，版本 2.5）
作者：@Leonxlnx · 许可以原仓库为准
用途：定方向之前读；决定"这个生意该长什么样"，而不是套通用 hero + feature grid。

## 何时读

- 不知道这个页面应该是什么调性；
- 产出反复变成同一套版式；
- 需要判断"暗色模式 / 重设计 / 上线前"该按什么顺序做。

## 核心：生意类型决定一切

taste-skill 的起点不是风格词，是**业务类型（kind）**，每种 kind 对应不同的页面计划：

| Brief | page type | kind | 含义 |
| --- | --- | --- | --- |
| App / SaaS / AI / 开发者工具 / 金融 | software | software | 卖的是软件本身 |
| 游戏、工作室发游戏 | software | gaming | 卖的是体验 |
| 硬件、设备（无人机、机械臂、键盘） | product | tech | 卖的是器物 |
| 其他实体商品（椅子、自行车、咖啡豆） | product | other | 卖的是货 |
| 有人被雇佣：诊所、律所、代理、工作室 | service | other | 卖的是专业能力 |
| 有人走进门：咖啡馆、酒吧、烘焙、民宿、车店 | place | other | 卖的是"到场" |

规则：**place 类以照片主导**（整页 12–20 张真实照片，首屏就要有"人在这里"的现场感）；
product 类以产品与细节图主导；software 类以界面/数据/工作流截图主导；service 类以人、案例、资质主导。
用同一套 hero + 三卡片 + 客户 logo 墙去做 place 或 service，是最典型的模板错误。

## 其余四个模块

1. **三旋钮**：布局变化 8 / 动效强度 6 / 信息密度 4（默认值，按 kind 调；后台 density 上调、motion 下调）。
2. **设计系统映射**：有 Material / Fluent / Carbon / Polaris / Radix / shadcn 可用时优先用，只在 token 层替换品牌色字型，不重写组件。
3. **暗色模式协议**：默认双模式，先定亮色再推导暗色；语义 token 换值不换结构；不用纯黑纯白；两套主题层级关系一致。
4. **preflight**：交付前按"对比度 / 间距 / 类型 / 状态 / 真实内容 / 响应式 / 键盘"逐项过，缺一项不算完成。

## 重设计审计顺序

先截图记录现状 → 只评审不动手（输出问题清单）→ 保留内容、行为、品牌资产 →
按"字型 → 色彩 → 框架边距 → 状态 → 替换模板构件"的顺序改 → 前后截图并排对比。
**不要在要丢弃的旧风格上做抛光。**

## 与本研究的关系

taste-skill 提供"业务类型 → 页面计划"的映射与三旋钮；
`art-direction.md` 把它与 frontend-design 的 token 先行、三种默认长相合并成一条可执行路径。
