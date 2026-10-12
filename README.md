# 求真分析 2.0（Fact-Based Analysis）

一个面向上市公司和投资机会的决策型研究技能。输入股票代码、公司名称或投资比较问题后，按“先证伪、充分研究、独立判断、可复算估值、明确决策”的标准工作。

当前主分支统一使用求真分析 2.0。旧版内容保留在 [求真分析 1.0 旧版归档](https://github.com/JohnWish1590/Fact-Based-Analysis/releases/tag/v1.0.0)。

## 核心要求

- 先验证事实、数据口径、逻辑链条和反面证据，再形成判断。
- 明确区分公司质量、当前价格和未来一至两年的投资回报。
- 多家公司必须比较商业模式、估值、预期收益和风险调整价值，并明确选出更优者。
- 原则上给出当前价格、合理估值、理想买入价、一年目标价、两年目标价、乐观情景价和悲观情景价。
- 每个价格都必须能够反向推导：经营假设 → 财务指标 → 估值方法与参数 → 股权价值 → 每股价格。
- 明确列出能够证伪当前判断的可观察条件。
- 数据不足时主动检索；仍无法可靠定价时，明确说明原因，不编造精确目标价。

## 安装

### Codex

在终端运行：

~~~bash
mkdir -p ~/.codex/skills
git clone https://github.com/JohnWish1590/Fact-Based-Analysis.git ~/.codex/skills/stock-truth-analysis
~~~

重新打开 Codex 后，技能可按相关请求自动触发，也可显式使用：

~~~text
$stock-truth-analysis 求真分析 000792 盐湖股份
~~~

更新技能：

~~~bash
git -C ~/.codex/skills/stock-truth-analysis pull
~~~

### ChatGPT 或其他支持 Agent Skills 的产品

下载本仓库，将根目录作为技能文件夹导入。技能入口文件是 SKILL.md，界面元数据位于 agents/openai.yaml。不同产品的导入入口和技能目录可能不同，请按对应产品的 Skills/技能导入界面操作。

## 输出结构

1. 直接结论：值不值得投资、当前贵不贵、是否会买。
2. 核心估值表：所有价格、时间点、情景和推导依据。
3. 三至五个决定性因素：只保留真正影响估值的内容。
4. 改变判断的条件：可观察、可验证、能触发重新估值。
5. 最终行动：买入、持有、等待、卖出、回避或证据不足无法可靠定价。

## 使用示例

~~~text
$stock-truth-analysis 求真分析 02617.HK，给出合理估值、理想买入价和两年目标价
~~~

~~~text
$stock-truth-analysis 比较两家公司哪一家风险调整后的投资价值更高，并明确选择
~~~

~~~text
$stock-truth-analysis 反推当前股价隐含的增长预期，并给出可复算的情景估值
~~~

## 文件结构

~~~text
.
├── SKILL.md
├── README.md
├── CHANGELOG.md
└── agents/
    └── openai.yaml
~~~

本技能提供研究和决策框架，不替代实时核实。市场价格和公司披露会随时间变化，每次使用都应重新检索，并注明数据日期、来源和估值假设。

## 版本

- 当前版本：[求真分析 2.0](https://github.com/JohnWish1590/Fact-Based-Analysis/releases/tag/v2.0.0)
- 历史版本：[求真分析 1.0（旧版归档）](https://github.com/JohnWish1590/Fact-Based-Analysis/releases/tag/v1.0.0)
