# Mi姐 skill（mi-jie-skill）

一个给 Cursor / Claude 类 Agent 用的 **skill**。它把 Mistery（粉丝称“Mi姐”，X：[@wr0789](https://x.com/wr0789)）的趋势交易知识和思维框架整理成 Agent 可以直接加载、照着执行的规则。

> ⚠️ **免责声明**：本项目仅供个人学习交流，**不构成任何投资建议**。内容来自公开推文和粉丝汇编资料，粉丝整理的文字可能和她的原话有出入。市场有风险，决策请自行负责。本项目与 Mistery 本人无关，也没有得到她的授权或背书。

## 它能做什么

1. **讲框架**：把她的体系（M0–M10，共 11 个模块）讲清楚，包括流动性、大盘→板块→个股、支撑压力、左侧/右侧、仓位、筹码、心理、交易体系，并标出推文链接或 PDF 页码。
2. **中肯分析**：用她的框架分析一个行情问题。固定写法是“环境 → 结构 → 两种情景及失效条件 → 按仓位分别说 → 框架的局限”，不喊单，不渲染情绪。
3. **风格仿写**：按她发推的语言风格写观点，比如【】标题、“宝宝们”、对仗金句、“耐心读完”。仿写内容会标明“风格仿写，非本人观点”。

## 目录结构

```
mi-jie-skill/
├── SKILL.md                    # Agent 加载入口：约束、框架、心智模型、输出模式、风格指南
├── references/
│   ├── framework.md            # M0–M10 详细地图（PDF 页码 + 推文 ID）
│   ├── style-examples.md       # 风格要点 + 真实推文链接 + 仿写模板
│   └── update-log.md           # 每日更新日志
├── updates/                    # 每晚增量写入的新推文摘要
├── scripts/README.md           # 夜间更新任务说明
├── NOTICE.md                   # 使用许可与来源说明
└── README.md
```

## 安装与使用

**Cursor**
```bash
git clone https://github.com/xtowerlink/mi-jie-skill.git ~/.cursor/skills/mi-jie
```
也可以放在项目里的 `.cursor/skills/mi-jie/`。Agent 会读取 `SKILL.md` 的 frontmatter，遇到相关问题时自动加载。

**Claude Code / Claude 风格的 skills**
```bash
git clone https://github.com/xtowerlink/mi-jie-skill.git ~/.claude/skills/mi-jie
```

**其他 Agent**：把 `SKILL.md` 的内容作为系统提示或知识文件加载，需要细节时再读 `references/`。

**示例提问**
- “用 Mi姐 的框架讲讲左侧和右侧抄底的区别”
- “我五成仓位，指数跌破了前期平台，按她的思路怎么看？给出中肯分析”
- “用 Mi姐 的推文风格写一条关于‘别急着回本’的短推”

## 更新频率

仓库主人的 Grok Bot 每晚约 **22:00（Asia/Tokyo，北京时间 21:00）** 跟踪 @wr0789 的新推文，把摘要追加到 `updates/` 和 `references/update-log.md`，并推送到本仓库。出现新的框架性提法时，同步更新 `SKILL.md`。没有新推文的日子不提交。

当前基线：初始语料截至 2026-10-26 21:27（JST），共 3,108 条；增量见 `updates/`，`.last_id` 现为 2115430906748101119（2026-10-28）。粉丝汇编 PDF 为 710 页版（2025-12-28）。

## 致谢与来源

- **Mistery（@wr0789）**：所有思想与观点归原作者所有。
- **《Mistery趋势交易论》**：由粉丝把她过往的推文和长文汇编而成，PDF 页脚注明“仅供免费阅读与分享”。本项目只引用页码和要点，不收录原文。
- 结构上参考了社区里的几个蒸馏仓库（mytestlook/mistery-trend-trading、fengeail/mi-jie-trend-trading-skills、Beney88/mistery-trend-trading、Samuel86-star/trend-judgment），没有复制其内容。

如果原作者认为有不妥之处，请提 issue，我们会立即修改或删除。
