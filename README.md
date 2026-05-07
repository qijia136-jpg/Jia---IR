# C-Level Assistant Tools

这是一个面向生物医药公司管理层的本地网页工具集。项目把 IR、融资筛选、战略招聘、注册策略、临床质量、供应链、合同模板和临床报告模板等高频管理任务，整理成可打开、可交互、可复用的 HTML 页面。

所有页面目前都是静态 HTML 文件，可以直接用浏览器打开，不依赖后端服务。

## 页面目录

| 文件 | 页面 / 工具 | 主要用途 |
| --- | --- | --- |
| `investor_agent_public_app.html` | 医疗投资人 Agent | 根据公司画像、融资阶段、地区、技术方向和合作方式推荐基金、CVC、药企、MNC、长线资本和亚洲资本；支持投资人查询、BD 合作筛选、港股 / 美股 / ODI / cornerstone 等判断。 |
| `index_HR.html` | IASO 战略招聘推荐 Agent | 根据公司战略反推关键岗位，输出招聘优先级、岗位池、能力矩阵、Mapping 方向、面试验证重点和推荐风险。 |
| `index_HR_copy.html` | IASO 战略招聘推荐 Agent 增强版 | 在战略招聘推荐基础上增加 LinkedIn 搜索策略、候选人评估体系、候选人外联模板等更偏执行层的内容。 |
| `quality_management_agent.html` | CAR-T 医学质量管理 Agent | 支持患者管理、治疗流程模拟、质量审核和管理报告生成，面向 CAR-T 临床、质量、生产和供应链团队。 |
| `Phase_III_CSR_Template.html` | Phase III 临床研究总结报告模板 | 提供 Phase III CSR 的完整章节结构，包括 synopsis、研究背景、人群、方法、统计、疗效、安全性、讨论、结论和附录。 |
| `regulatory-strategy.html` | 国际注册策略教学 | 以福可苏和 in vivo 产品全球申报为案例，拆解市场选择、数据策略、监管路径、临床开发、CMC / 供应链和商业化假设。 |
| `cgt-supply-standalone.html` | CGT 出海分选中心与供应链策略 | 围绕 FUCASO / CGT 出海，比较欧洲、北美、南美的市场、人群、分选中心、认证流程和扩产能路径。 |
| `Japan.html` | 日本进口单采血流程报告 | 梳理日本单采血进口至中国的业务概览、采集医院、端到端流程、海关风评材料、时间线、干系人和生物安全控制。 |
| `日本单采血进口流程报告(1).html` | 日本进口单采血流程报告副本 | 与 `Japan.html` 内容相近，可作为备用版本或样式 / 内容迭代版本。 |
| `contract.html` | 合同模板库 | 统一展示采购、工程、服务、研究中心协议、NDA、MTA、人资、病毒业务、销售 / 经销等合同模板，支持搜索、筛选和统计。 |

## 核心模块

### 1. IR 与融资 / BD

核心页面是 `investor_agent_public_app.html`。它内置投资人数据库，并按项目画像进行打分和排序，适合 CEO、CFO、BD、IR 团队做融资准备和合作方筛选。

当前覆盖的对象包括：

- 全球生命科学 VC、growth equity、crossover 和二级市场基金
- 药企 CVC、MNC、BD / licensing 对手方
- 中国、香港和亚洲医疗基金
- 主权基金、险资、家族办公室和长期机构资本
- ATMP、CAR-T、gene therapy、delivery platform、AI / techbio 等细分方向

### 2. 战略招聘

`index_HR.html` 和 `index_HR_copy.html` 用于把公司战略翻译成招聘决策。页面关注的不是泛泛招聘流程，而是判断当前阶段应该优先补哪类能力。

适用场景包括：

- 全球化临床、注册、CMC、质量、供应链和商业化团队搭建
- 高管岗位优先级判断
- 目标公司池和候选人 mapping
- 面试验证问题、风险点和外联话术准备

### 3. 质量管理与临床运营

`quality_management_agent.html` 把 CAR-T 医学质量管理拆成患者管理、流程模拟、质量审核和报告生成四个工作台。

它适合用于：

- 患者准入和风险提示
- 细胞采集、生产、放行、冷链、回输、随访的流程复盘
- GMP / GSP / 内部质量审核 / CAPA 相关输出
- 周期性质量管理报告

### 4. 注册、CSR 与供应链

这些页面服务于临床开发、注册申报和全球供应链规划：

- `Phase_III_CSR_Template.html`：Phase III CSR 写作骨架和章节模板。
- `regulatory-strategy.html`：国际注册策略教学页面。
- `cgt-supply-standalone.html`：CGT 全球分选中心、认证流程和产能扩展策略。
- `Japan.html` / `日本单采血进口流程报告(1).html`：日本单采血进口、海关风评和生物安全管理流程。

### 5. 法务与合同模板

`contract.html` 是合同模板索引页，便于在一个页面里快速检索和筛选常用模板。

目前包含的分类包括：

- 采购相关
- 工程相关
- 服务相关
- 研究中心协议
- 保密协议
- 材料转移协议
- 人资相关
- 病毒业务
- 销售 / 经销相关

## 使用方式

1. 打开项目文件夹。
2. 双击需要的 `.html` 文件，或在浏览器中直接打开。
3. 如果浏览器限制本地脚本，可以用任意静态服务器打开，例如 VS Code Live Server。

## 维护建议

- 投资人数据主要维护在 `investor_agent_public_app.html` 的 JavaScript 数组中。
- 合同模板条目主要维护在 `contract.html` 的 `templates` 数组中。
- HR、质量、注册和供应链页面目前是单文件静态应用，样式、数据和逻辑都在各自 HTML 内。
- 如果后续页面继续增多，建议增加一个 `index.html` 作为统一入口页，把这些工具按 IR、HR、Clinical / Regulatory、Legal / Contract 分组导航。

## 注意

这些页面用于内部分析、教学和管理辅助，不能替代正式法律意见、监管沟通、临床医学判断、质量体系文件或公司审批流程。
