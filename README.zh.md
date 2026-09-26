<div align="center">

# AI 安全攻防综述

**四篇证据综述：LLM 与智能体、图像与视频生成、具身闭环、世界模型。**

<sub>4 篇 · 21 万汉字 · 251 页 PDF · 附英文译本</sub>

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC_BY--NC--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)  ·  [![Status](https://img.shields.io/badge/Status-compiled_draft-orange)](#状态与边界)  ·  [![Language](https://img.shields.io/badge/Language-English_%7C_%E4%B8%AD%E6%96%87-blue)](#语言与版本)  ·  [![图谱](https://img.shields.io/badge/%E5%9B%BE%E8%B0%B1-97_%E7%AF%87-informational)](release/zh/图谱_97篇索引.md)

[English](README.md) · [简体中文](README.zh.md)

</div>

> 知彼知己，百战不殆。
>
> — 《孙子兵法·谋攻》

---

## 主题

四篇问的是同一个问题，只是换了领域：**哪个功能接口最先守不住自己的安全合同，本来该在哪里把它中断？**

这个问法让四篇之间可以对照。反过来说，"攻击成功率"在不同论文之间是**不可比**的——除非统计单位、
成功条件和攻击预算三项对齐。所以每篇都把分母和数字写在一起，并且**拒绝合并那些不能合并的结果**。

| Language | README | Documents |
|---|---|---|
| **简体中文** | 本文件 | 四篇中文原稿 + 图谱索引，21 万汉字，251 页 PDF |
| **English** | [README.md](README.md) | four surveys, 160k words, 335 pages of PDF |

[主题](#主题) · [概述](#概述) · [文件](#文件与格式) · [学习路径](#学习路径) · [引用](#引用) · [路线图](#截止与后续纳入) · [许可](#许可) · [贡献](#参与贡献)

## 概述

四篇互相独立的证据综述。它们共用同一套分析工具，所以先花 30 分钟掌握下面五件工具，之后每篇都能快很多。

| 工具 | 一句话 | 在哪学 |
|---|---|---|
| **首破接口** | 不问"是什么攻击"，问哪个功能接口第一个失效 | 四篇都有专章，LLM 第 4 章最紧凑 |
| **安全合同** | 每个接口都有输入/输出条件；攻击破坏合同，防御恢复合同 | 视觉第 3 章、具身第 4 章 |
| **有效分母** | 百分比只有在单位、成功条件、预算、证据层四项对齐时才可比 | 视觉第 2 章、具身第 9 章 |
| **四联报告** | 攻击效果 / 残余风险 / 正常效用 / 部署成本 | 世界模型第 4 章 |
| **复现阶梯** | "运行了什么"决定"只能证明什么" | 各篇的复现审计章 |

## 文件与格式

每篇都提供 Markdown（在 Git 上直接读）与 PDF（下载看，图已内嵌）。

## 四篇综述

### ① 从模型越狱到系统隔离
*LLM and Multimodal Agent Security: An Evidence-Grounded Taxonomy*

| | |
|---|---|
| 中文 | [从模型越狱到系统隔离.md](release/zh/从模型越狱到系统隔离.md) · [47 页](release/zh/从模型越狱到系统隔离.pdf) |
| English | [LLM-and-Multimodal-Agent-Security.md](release/en/LLM-and-Multimodal-Agent-Security.md) · [50 页](release/en/LLM-and-Multimodal-Agent-Security.pdf) |
| 篇幅 | 约 2 小时 · 11 章 |
| 结构 | 语料与编码方法 → 背景与输入输出合同 → 分类设计与覆盖审计 → 防御方法家族 → 跨家族综合 → 数据指标与评价证据 → 事件复现与部署映射 → 挑战与证据限制 |

- [ ] 第 4 章**分类设计**——唯一主分类轴
- [ ] 第 6 章**防御方法家族**——为什么"加一层过滤器"不是防御家族
- [ ] 第 9 章**证据限制**——作者明确说哪些结论不能下
- [ ] 读完能回答：越狱与提示注入差在哪？为什么不存在一个"LLM 总体攻破率"？

### ② 从首破接口到纵深防御
*Image and Video Generation Security: An Evidence Review*

| | |
|---|---|
| 中文 | [从首破接口到纵深防御.md](release/zh/从首破接口到纵深防御.md) · [136 页](release/zh/从首破接口到纵深防御.pdf) |
| English | [Image-and-Video-Generation-Security.md](release/en/Image-and-Video-Generation-Security.md) · [203 页](release/en/Image-and-Video-Generation-Security.pdf) |
| 篇幅 | 约 7 小时 · 12 章 + 4 附录 |
| 结构 | 证据治理 → 系统边界与威胁模型 → I1–I7 分类 → 镜像证据综合 → 跨接口纵深防御 → 视频专项 → 工程检验 → 部署决策 → 局限与双用途 → 可证伪议程；附录含 27 项论文深析与 32 张事件卡 |

- [ ] 第 2 章**证据治理**——132 条引文、10 幅图、18 张表的可审计口径
- [ ] 第 4 章 **I1–I7 接口分类**——全篇骨架
- [ ] 第 7 章**视频专项**——时间、运动、音画联合身份
- [ ] 附录 C——**32 张事件卡**
- [ ] 读完能回答：同一段假视频可能"首先"失效在哪些位置？

### ③ 从看错到做错
*Closed-Loop Security of VLM, VLA, and World-Action Models*

| | |
|---|---|
| 中文 | [从看错到做错.md](release/zh/从看错到做错.md) · [46 页](release/zh/从看错到做错.pdf) |
| English | [Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.md](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.md) · [64 页](release/en/Closed-Loop-Security-of-VLM-VLA-and-World-Action-Models.pdf) |
| 篇幅 | 约 3 小时 |
| 附赠 | [图谱_97篇索引.md](release/zh/图谱_97篇索引.md)——97 篇逐篇算法图谱链接版（论文 + arXiv + 许可 + 机制要点） |

- [ ] 第 4 章**技术脉络与系统合同**——回答安全 vs 行动安全
- [ ] 第 5 章**闭环攻击 taxonomy**
- [ ] 第 7 章**跨家族综合**——什么时候选哪一层控制
- [ ] 翻[图谱索引](release/zh/图谱_97篇索引.md)，挑 3 篇论文点进去
- [ ] 读完能回答：VLM 看错和 VLA 做错是同一个问题吗？

### ④ 从想象世界到控制现实
*World Model Security: Attacks and Defenses across World, Environment, Action, and Control Models*

| | |
|---|---|
| 中文 | [从想象世界到控制现实.md](release/zh/从想象世界到控制现实.md) · [22 页](release/zh/从想象世界到控制现实.pdf) |
| English | [World-Model-Security.md](release/en/World-Model-Security.md) · [22 页](release/en/World-Model-Security.pdf) |
| 篇幅 | 约 1 小时 · 17 章 |
| 结构 | 概念边界 → 检索方法 → 威胁模型 → 攻击面 → 防御与恢复 → 代表性文章解析 → 产品实体解析 → 部署风险 → 不可合并的结果 → 新闻与治理 → 代码审计 → 跨家族综合 → 未来趋势 → 局限 |

- [ ] **概念边界**一章——WM / EWM / WAM / WCM 怎么分
- [ ] **攻击面**一章——从供应链到现实执行
- [ ] **不可合并的结果**——作者为什么正式拒绝做荟萃合并
- [ ] 读完能回答：为什么预测与动作耦合是风险放大器，但耦合本身不等于不安全？

### 旧稿留档

[中文](release/zh/旧稿_从越狱到执行边界.md) · [English](release/en/Old-Draft_Jailbreaking-to-Execution-Boundaries.md) · [PDF 43 页](release/en/Old-Draft_Jailbreaking-to-Execution-Boundaries.pdf)

① 的前身，为溯源保留。1,398 个内容单元已逐项处置：442 迁入正文、827 进附录、129 明确排除。
**新读者请直接读 ①。**

## 学习路径

| 路径 | 顺序 | 时间 |
|---|---|---|
| 威胁建模入门 | 五件工具 → ① → ④ | 约 4 小时 |
| 生成式视觉专题 | 五件工具 → ② → 图谱索引 | 约 9 小时 |
| 机器人 / 具身专题 | 五件工具 → ③ → ④ | 约 5 小时 |

## 语言与版本

中文是**原稿**；英文是**重写过的母语英文译本**，工序为「忠实翻译 → 母语英文重写 → 对照中文独立核查」。
段落不一一对应，但主张、数字、限定语与引用完全一致。

## 仓库结构

```
.
├── README.md          英文说明
├── README.zh.md       本文件（中文）
├── CITATION.cff       机器可读引用元数据
├── LICENSE            CC BY-NC-SA 4.0
└── release/
    ├── en/            四篇 + 旧稿留档（Markdown + PDF）
    └── zh/            中文 Markdown + PDF + 图谱_97篇索引.md
```

另有 `source/` 目录存放结构化源（`paper.json`、图、证据台账），不进仓库。

## 更新日志

### v0.2.0 — 2026-09-26
- **每篇文稿新增「截止后更新」附录**，登记检索于 2026-09-26 的新材料。
- OpenAI—Hugging Face 事件由"报告未发布"更新为有据可查的案例，含披露机制、报道规模、政府范围与参议院调查。
- 另登记 8 起事件、9 篇论文、2 个 CVE、4 项监管动向与 2 项来源凭证合作，并逐条注明影响的章节。
- 中英 PDF 全部重出，附录在每种格式中都可读到。

### v0.1.0 — 2026-09-26
- 首次公开发布：中文原稿与重写后的英文译本。
- 对全部文档做英文重写，随后逐片段独立核查。
- 抽样章节对做对照中文原稿的抽查；所有 high 与 medium 问题已修复。
- 新增 `LICENSE`（CC BY-NC-SA 4.0）与 `CITATION.cff`。

## 截止与后续纳入

**各篇截止：** LLM 2026-08-06 · 生成式视觉安全 2026-08-09 · 具身闭环 2026-08-06 · 世界模型 2026-08-09。检索更新于 2026-09-26。

**已写入正文。**

- **OpenAI—Hugging Face 事件从"未发布"变为有据可查的案例。** OpenAI 于 2026-09-16/17 公开事件说明与
  披露机制；报道称涉事智能体约 700 个、触及数十个第三方系统、53 张用户图片外泄、生成约 100 万条
  编码链接；受影响政府站点含澳大利亚；美国参议院启动调查。各稿记录此事、说明它改变了什么，并保留
  原有边界判断——逐动作归因仍然未知。
- **新增事件**——西班牙首次受理"由 AI 代理导致"的数据泄露通报；欧洲多国 AI 生成"抗议"视频；
  印度喀拉拉邦伪造警官视频立案；商用两足机器人两个 root RCE，其一可经蓝牙免配对利用。
- **新增论文**——多智能体提示注入；有效性感知的越狱评测；推理通道前缀攻击；护栏可解释性；
  紧凑生成式护栏；DUMA-Bench；面向 flow-matching VLA 的 DRIFT；两篇世界模型安全架构。
- **新增漏洞**——CVE-2026-77519（MaxKB）与 CVE-2026-47250（mcp-server-kubernetes），都落在
  工具与执行这条链上。
- **监管与产业**——中国标识制度；欧盟委员会首次动用 AI Act 调查权；美国州总检察长呼吁立法；
  NIST/CSA 智能体红队指南；Sony × Reuters 与 AFP × Dalet 的新闻编辑室来源工作。


### 截止后发现并已登记的材料（检索于 2026-09-26）

**事件**

- **2026-07** — OpenAI 内部网络安全评估中，其模型绕过为它们设置的控制，触及数十个第三方网站与服务
- **2026-09-17** — OpenAI 公开该事件说明，并承诺建立安全事件披露机制
- **2026-09-24** — 报道称模型渗透澳大利亚政府网站以获取非公开数据，被描述为首例政府被 AI 入侵
- **2026-09** — 西班牙 AEPD 首次收到"由 AI 代理执行的攻击导致"的个人数据泄露通报
- **2026-09-25** — 欧洲多国出现 AI 生成的"抗议"视频
- **2026-09** — 印度喀拉拉邦：就伪造高级警官的 AI 视频立案
- **2026-09** — Unitree G1 EDU 人形机器人两个 root RCE 漏洞，其一可经蓝牙免配对利用；报道称可近距离接管并"人传人"扩散

**论文与预印本**

| Paper | Venue | Topic |
|---|---|---|
| Beyond Single-Model Injection: a threat model and defense architecture for prompt injection in multi-agent systems | arXiv 2609.22949 | 多智能体提示注入 |
| Validity-Aware Jailbreak Evaluation for Large Language Models | EMNLP 2026 main | 越狱评测的有效性 |
| Prefilling the Reasoning Channel: Output-Prefix Attacks on Reasoning LLMs | preprint | 推理通道前缀攻击 |
| Decoding Guardrails: XAI-Guided Perturbation Analysis of Prompt Injection Detection | preprint | 护栏可解释性 |
| HiveTraceGuard-Pro: a compact generative guardrail for prompt injection, jailbreaks and obfuscation | preprint | 生成式护栏 |
| DUMA-Bench: a dual-control multi-agent benchmark for evaluating LLM agent security | benchmark | 智能体安全基准 |
| DRIFT: derailing trajectories of flow-matching VLAs with adversarial patch attack | arXiv 2608.03207 | VLA 对抗补丁 |
| Denying the World Model: automated moving target defense as an architectural countermeasure | preprint | 世界模型对抗移动目标防御 |
| UAWM: a unified adaptive world model with multi-layer security | preprint | 世界模型安全架构 |

**漏洞**

- **CVE-2026-77519** — MaxKB——RAG/智能体平台
- **CVE-2026-47250** — mcp-server-kubernetes——MCP 工具服务器

**标准与监管**

- 中国：AI 生成内容标识义务的监管体系，以及 9 月关于标识管理"从技术规则到技术标准"的解读
- 欧盟：欧盟委员会首次动用 AI Act 的调查权
- 美国：州总检察长呼吁国会立法；业界指出 AI 代理的监管空白
- NIST / CSA：AI 代理红队指南与治理标准
- 来源凭证：Sony 与 Reuters 展示近乎实时的新闻编辑室真实性工作流；AFP 与 Dalet 合作新闻视频来源

**基准与工具**

- DUMA-Bench——双控多智能体 LLM 安全评测基准
- 比利时一家安全公司发布开放权重的 AI 安全评测模型

**本版遗留、下一版补齐的缺口**

| 类别 | 具体内容 | 当前状态 |
|---|---|---|
| 方法 | 1,854 条检索候选的逐条标题/摘要/全文排除日志 | 未完成，因此本版不声称穷尽覆盖，也不伪造 PRISMA 纳入数 |
| 术语 | EWM 与 WCM 的边界 | 领域用法尚未稳定；本文的功能分类为可比性而设，不取代作者或产品的原始命名 |
| 复现 | 27 项统一论文深析的 `reproduction_status` | 全部为 `NOT_ATTEMPTED`；七个公开仓库仅 `STATIC_AUDIT_ONLY` |
| 产品 | Happy Oyster 与 MoWorld 的功能定级 | 公开证据不足以判为 WAM/WCM，也无法据此得出产品安全结论 |

**生成式视觉安全：十四项可证伪议程（做完即纳入）**

每项都写明预测、最低实验与否证条件；否证条件成立时，综述应撤回或降级原判断。

- [ ] F01 · 图像安全防御不能无条件迁移到视频
- [ ] F02 · 时空后门会跨架构规避单帧审核
- [ ] F03 · 联合音画生成会削弱依赖不同步的取证
- [ ] F04 · 实时水印的瓶颈将从离线准确率转向首次告警时延与状态
- [ ] F05 · LoRA 与运动模块的组合风险高于单模块审计
- [ ] F06 · 概念擦除的真正边界是多条件可恢复性
- [ ] F07 · 视频训练数据记忆需要事件级定义
- [ ] F08 · 生成服务可用性是独立安全接口
- [ ] F09 · 水印与 C2PA 只能作为互补链验证
- [ ] F10 · 检测器必须显式建模低基率和适应性攻击
- [ ] F11 · 个性化同意必须支持可验证撤回
- [ ] F12 · 事件级因果链优先于新闻计数
- [ ] F13 · 检测更快不必然带来更好的受害者救济
- [ ] F14 · 代理化生成将把单轮内容安全变成状态化策略安全

## 状态与边界

- 四篇状态均为 **`compiled-draft`**，**不是投稿就绪版本**。
- **未做事实核验**：论文结论、CVE、法规条文按原样表达，外部链接未访问。
- 荟萃分析因可比性不足**正式拒绝合并**（零个可合并组）——不报告任何伪造的总体攻破率。
- 图谱**只提供链接**：97 篇源论文中只有 41 篇的插图许可支持再分发（46 篇为 arXiv 非独占许可，4 篇 CC BY-NC-ND）。
- 英文 PDF 由 Markdown 经无头 Chrome 渲染。
- **数据截止 2026-08-09。**

## 引用

```bibtex
@misc{surveys2026,
  title        = {AI Security Surveys: LLM, Generative Vision, Embodied Loops, and World Models},
  author       = {Mingjun Cheng},
  year         = {2026},
  version      = {v0.2.0},
  howpublished = {\url{https://github.com/ManfredCh/ai-security-surveys}},
  note         = {整稿候选，数据截止 2026-08-09。许可：CC BY-NC-SA 4.0}
}
```

若只引用其中一篇，请用它自己的标题，并以 `release/zh/<篇名>.md` 作为定位。引用元数据见
[CITATION.cff](CITATION.cff)，作者为 `Mingjun Cheng`（程明骏，Vorynel Co.td）。

## 参与贡献

这是整稿候选，已知还有缺口，欢迎指正与补充。

**提 issue 适用于**

- 事实错误：注明章节与段落，并给出你的依据
- 应该纳入但缺席的论文、标准或事件
- 翻译问题：贴出英文句子与它对应的中文
- 失效链接、页数错误、排版问题

**欢迎 PR**：有依据的更正、按附录 D 统一术语的修正、新增译本。PR 需说明改了什么、为什么改，
并附依据。

**不接受**

- 没有新证据却改动主张强度、适用范围或限定语的"重写"
- 无来源的增补
- 改变段落主张的"润色"

**其他语言译本**欢迎，沿用同一许可（CC BY-NC-SA 4.0）：保留署名、保留许可、注明是译本。

## 致谢

- 正文引用的每一篇论文、项目、标准与事件报告——本稿是对它们工作的综合。
  [AI 安全攻防综述](https://github.com/ManfredCh/ai-security-surveys)里的逐篇图谱直接链接了其中 97 篇。
- 各轮审校以独立模型通道完成，记录保存在本地而不公开。
- **AI 使用声明**：本稿在结构整理、翻译与英文重写上使用了 AI 辅助。每一份译文与重写都经过
  对照中文原稿的独立核查；数字、限定语、引用与技术术语均经程序化校验。
  内容责任由作者承担，不在工具。

## 星标趋势

<a href="https://star-history.com/#ManfredCh/ai-security-surveys&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-surveys&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=ManfredCh/ai-security-surveys&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=ManfredCh/ai-security-surveys&type=Date" width="600" />
  </picture>
</a>

<div align="center">

[![Stars](https://img.shields.io/github/stars/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/stargazers)  ·  [![Forks](https://img.shields.io/github/forks/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/forks)  ·  [![Issues](https://img.shields.io/github/issues/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/issues)  ·  [![Last commit](https://img.shields.io/github/last-commit/ManfredCh/ai-security-surveys)](https://github.com/ManfredCh/ai-security-surveys/commits)

</div>

## 许可

<a rel="license" href="https://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a>

正文、图与表采用
**[知识共享 署名—非商业性使用—相同方式共享 4.0 国际](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh)**
（CC BY-NC-SA 4.0）许可。完整法律文本见 [LICENSE](LICENSE)。

| 你可以 | 条件是 |
|---|---|
| **共享**——以任何媒介复制与传播 | **署名**——注明作者、附许可链接、说明是否修改 |
| **演绎**——修改、转换或基于本作品创作 | **非商业性使用**——不得用于商业目的 |
| | **相同方式共享**——你的贡献须以相同许可分发 |

**"相同方式共享"实际意味着**：别人翻译或改写本作品后，成果必须继续采用 CC BY-NC-SA，
不能改成"版权所有"。引用、链接、原样收录进合集**不会**触发这一条。

**它不限制作者本人**：许可是非独占的，作者仍可另以其他条款在其他地方发表。

**第三方材料不在本许可范围内。** 文中引用的论文、插图、产品名与商标归各自权利人所有。
逐篇图谱只提供链接，正是因为 97 篇源论文中只有 41 篇的插图许可支持再分发。

## 相关仓库

- **[Generative and Embodied AI Security](https://github.com/ManfredCh/ai-security-book)** — 统一书稿——6 部 24 章，一件工具贯穿四个领域
- **[AI Security Surveys](https://github.com/ManfredCh/ai-security-surveys)** — 四篇独立安全综述 + 97 篇图谱索引
- **[Foundations](https://github.com/ManfredCh/ai-security-foundations)** — 入门教程与两篇技术背景综述
