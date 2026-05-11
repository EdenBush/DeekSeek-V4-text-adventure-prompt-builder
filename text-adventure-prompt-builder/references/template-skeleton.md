# 模板骨架 — 固定区与可变区标注

> 本文档标注了提示词模板中哪些部分是固定不可修改的，哪些是需要根据用户输入填充的。
>
> **v5.5 模块化升级**：固定区已拆分为独立引用文件，提升可维护性。可变区保持不变。

---

## 固定区（独立引用文件）

固定区为提示词的核心规则，文字不得修改。各固定区现在存储在独立的引用文件中，SKILL.md 在构造提示词时按需读取：

| 章节 | 引用文件路径 | 说明 |
|-----|------------|------|
| FIXED SECTION A | `sections/fixed-core.md` | 思维模式要求 |
| FIXED SECTION B | `sections/fixed-core.md` | 特殊模式 |
| FIXED SECTION C | `sections/fixed-core.md` | Internal Process + Visible Output Format |
| FIXED SECTION D | `sections/fixed-core.md` | 深度推理要求 + V4 自检 + 思考线程隔离 |
| FIXED SECTION E | `sections/fixed-core.md` | 核心行为规则（结构化重构版） |
| FIXED SECTION E-BIS | `sections/fixed-core.md` | 叙事节奏控制系统 |
| FIXED SECTION E-TER | `sections/fixed-core.md` | 场景类型写作指南 |
| FIXED SECTION E-CINEMA | `sections/fixed-core.md` | 电影级主角代入模式专项规则（v5.4） |
| FIXED SECTION E-TERM | `sections/fixed-core.md` | 术语一致性锚定（v5.5） |
| FIXED SECTION E-QUAT | `sections/fixed-core.md` | 情感曲线管理 |
| FIXED SECTION E-QUAT-BIS | `sections/fixed-core.md` | 弹性陷阱机制 |
| FIXED SECTION E-SEPT | `sections/fixed-core.md` | 选择后果追踪系统 |
| FIXED SECTION E-OCT | `modules/e-oct.md` | 关系微变化系统 |
| FIXED SECTION E-NOV | `modules/e-nov.md` | NPC自主行动时钟 |
| FIXED SECTION E-PULSE | `modules/e-pulse.md` | 世界脉动系统 |
| FIXED SECTION E-TRANS | `modules/e-trans.md` | 高级转场技法 |
| FIXED SECTION E-RUMOR | `modules/e-rumor.md` | 流言/舆论网络 |
| FIXED SECTION E-DECA | `modules/e-deca.md` | 叙事错位引擎 |
| FIXED SECTION E-HAREM | `modules/e-harem.md` | 后宫关系管理系统 |
| FIXED SECTION E-R18 | `modules/e-r18.md` | NSFW成人内容增强 |
| FIXED SECTION E-ECCHI | `modules/e-ecchi.md` | 幸运色狼/福利事件系统 |
| FIXED SECTION F | `sections/fixed-core.md` | 回复格式 + 强制选项区块 |

---

## 可变区（在 template-skeleton.md 中保持不变）

以下可变区根据用户输入填充，章节文本继续保留在 template-skeleton.md 中：

- VARIABLE SECTION G — 故事核心概念 + 文风配置模板（完整模板保留在此文件中）
- VARIABLE SECTION F-BIS — 游戏体验配置（完整模板保留在此文件中）
- VARIABLE SECTION G-PLOT — 剧情深度系统（完整模板保留在此文件中）
- VARIABLE SECTION G-BLUEPRINT — 故事蓝图模板（完整模板保留在此文件中）
- VARIABLE SECTION H — 男主角设定模板（完整模板保留在此文件中）
- VARIABLE SECTION I — 女主角阵营模板（完整模板保留在此文件中）
- VARIABLE SECTION J — 故事舞台模板（完整模板保留在此文件中）
- VARIABLE SECTION K — 开场引导模板（完整模板保留在此文件中）
- VARIABLE SECTION K-FORMAT — 自适应回复格式（完整模板保留在此文件中）
- 结尾强制指令
- 最终输出结构（v3.0 模块化 — 按故事类型选择性组装）

---

## 最终输出结构（v3.0 模块化 — 按故事类型选择性组装）

```
【强制 ■ — 始终包含】
【思维模式要求】[FIXED SECTION A — 引用 sections/fixed-core.md]
<特殊模式>[FIXED SECTION B — 引用 sections/fixed-core.md]
[Internal Process][FIXED SECTION C — 引用 sections/fixed-core.md]
[Visible Output Format][FIXED SECTION C — 引用 sections/fixed-core.md]
【效果提示词——深度推理要求】[FIXED SECTION D — 引用 sections/fixed-core.md]
【核心行为规则】[FIXED SECTION E with name replacement — 引用 sections/fixed-core.md]
【叙事节奏控制系统】[FIXED SECTION E-BIS — 引用 sections/fixed-core.md]
【场景类型写作指南】[FIXED SECTION E-TER — 引用 sections/fixed-core.md]
【电影级主角代入模式专项规则】[FIXED SECTION E-CINEMA — 引用 sections/fixed-core.md]
【术语一致性锚定】[FIXED SECTION E-TERM — 引用 sections/fixed-core.md]
【情感曲线管理】[FIXED SECTION E-QUAT — 引用 sections/fixed-core.md]
【弹性陷阱机制】[FIXED SECTION E-QUAT-BIS — 引用 sections/fixed-core.md]
【选择后果追踪系统】[FIXED SECTION E-SEPT — 引用 sections/fixed-core.md，仅限think]

【模块化 □/○ — 按故事类型选择性包含】
[if E-OCT]  【关系微变化系统】[FIXED SECTION E-OCT — 引用 modules/e-oct.md]
[if E-NOV]  【NPC自主行动时钟】[FIXED SECTION E-NOV — 引用 modules/e-nov.md]
[if E-PULSE]【世界脉动系统】[FIXED SECTION E-PULSE — 引用 modules/e-pulse.md]
[if E-TRANS]【高级转场技法】[FIXED SECTION E-TRANS — 引用 modules/e-trans.md]
[if E-RUMOR]【流言/舆论网络】[FIXED SECTION E-RUMOR — 引用 modules/e-rumor.md]
[if E-DECA] 【叙事错位引擎】[FIXED SECTION E-DECA — 引用 modules/e-deca.md]
[if E-HAREM] 🆕 后宫关系管理 [FIXED SECTION E-HAREM — 引用 modules/e-harem.md]
[if E-R18]  🔞 NSFW增强模块 [FIXED SECTION E-R18 — 引用 modules/e-r18.md]
[if E-ECCHI] 🆕 幸运色狼/福利事件系统 [FIXED SECTION E-ECCHI — 引用 modules/e-ecchi.md]
---
[DM角色介绍段 — 含文风+格式类型+已激活模块一览]

🆕 【DM执行优先级】（v4.0 新增 + v5.0补充 — 从高到低）
1. 选择必须有可感知的后果 [E-SEPT 可感知性检查]
2. 场景类型决定写法 [E-TER]
3. 情感强度不能连续三红 [E-QUAT]
4. 关系变化通过肢体语言呈现 [E-OCT]
5. 🆕 后宫关系平衡检查 [E-HAREM — 后宫类故事强制]
6. 🆕 福利事件计数器检测 [E-ECCHI — 日常后宫类]
7. 叙事节奏A/B/C判断 [E-BIS]
8. 🆕 冲突预算检测（满10触发强制事件）[E-BIS 冲突预算池]
9. 🆕 故事蓝图阶段目标检查 [故事蓝图引擎]
10. 其他高级规则（仅专家模式生效）

## 一、故事核心概念 [VARIABLE SECTION G — 模板保留在此文件]
🆕 ## 二、故事蓝图（必填）[VARIABLE SECTION G-BLUEPRINT — 模板保留在此文件]
## 三、文风与叙事标准 [VARIABLE SECTION G — 模板保留在此文件]
## 四、游戏体验配置 [VARIABLE SECTION F-BIS — 模板保留在此文件]
[if G-PLOT] ## 五、剧情深度系统 [VARIABLE SECTION G-PLOT — 模板保留在此文件]
## 六、男主角 [VARIABLE SECTION H — 模板保留在此文件]
## 七、女主角阵营 [VARIABLE SECTION I — 模板保留在此文件]
## 八、次要角色 [VARIABLE — 模板保留在此文件]
## 九、故事舞台 [VARIABLE SECTION J — 模板保留在此文件]
## 十、自适应回复格式 [VARIABLE SECTION K-FORMAT — 模板保留在此文件]
## 十一、回复格式（默认）[FIXED SECTION F — 引用 sections/fixed-core.md]
## 十二、开场引导 [VARIABLE SECTION K — 模板保留在此文件]
【请在回复中重新从头进入详细描写游戏开场剧情】[FIXED]
```
