# concept-learning-lab

用 AI 构建的个人概念学习实验室：一个**可复用的概念学习资料生成 Skill** + 用它生成并经本人核查的**三份概念学习资料**（Agent / 大模型的上下文 / Skill）。

本仓库是 AI 课程作业一的成果，也是后续课程项目的个人工具基础——学任何新概念，都可以调用这里的 Skill 按同一套流程产出结构化学习页。

## 仓库结构

```
concept-learning-lab/
├── .workbuddy/
│   └── skills/
│       └── concept-learning/
│           └── SKILL.md                  ← 项目级 Skill（本仓库核心）
├── learning-materials/
│   ├── agent.html                        ← 概念学习资料：Agent
│   ├── llm-context.html                  ← 概念学习资料：大模型的上下文
│   ├── skill.html                        ← 概念学习资料：Skill
│   └── concept-relationship.md           ← 三概念关系说明（含 Mermaid 图）
├── README.md
└── .gitignore
```

## Skill：concept-learning

**位置**：`.workbuddy/skills/concept-learning/SKILL.md`（项目级，随仓库分发）

**它做什么**：输入任意概念名称，按"先查证、再解释、后自测"的固定流程生成一份结构化 HTML 学习页，包含 9 个模块：学习目标、核心问题、个人化解释、核心机制、应用场景、概念辨析、自测题、参考来源。

**硬性约束**（写进了 Skill 本体）：

- 至少 3 个真实可公开访问的来源，逐个验证存在，禁止编造——宁少勿假
- 关键事实必须与来源一致；"我的解释"必须第一人称、禁止整段照搬
- 生成后按自检清单逐项检查，不通过不交付

### 如何在 WorkBuddy 中调用

1. 在 WorkBuddy 中打开本仓库文件夹（项目级技能自动加载，技能加载机制见 [WorkBuddy 官方文档·技能](https://www.workbuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)）
2. 在对话中直接说：**"用 concept-learning 学习『强化学习』"**（可加难度/受众参数）
3. 产出自动保存到 `learning-materials/<概念名>.html`

本仓库的三份学习资料即由该 Skill 生成（生成过程中来源均经检索验证）。

## 已生成的学习资料

| 文件 | 概念 | 一句话概括 |
|------|------|-----------|
| [agent.html](learning-materials/agent.html) | Agent | 在循环中自主使用工具的 LLM——"长出手脚的大模型" |
| [llm-context.html](learning-materials/llm-context.html) | 大模型的上下文 | 模型每次回答时能看到的全部信息，既是工作记忆也是稀缺资源 |
| [skill.html](learning-materials/skill.html) | Skill | 把高频任务的做法固化成文件夹，让 AI 按需翻阅的操作手册 |
| [concept-relationship.md](learning-materials/concept-relationship.md) | 三者关系 | Agent 是行为层、上下文是认知层、Skill 是知识层 |

## 人工核查与 AI 使用说明

**AI 完成的部分**：Git 环境检查与配置、仓库克隆、Skill 初稿、三份学习资料初稿（按 Skill 流程执行，含来源检索验证）、本 README 初稿、Git 提交与推送操作。

**本人完成/核查的部分**（按时间顺序）：

1. **仓库与命名**：创建 GitHub 仓库并确定仓库名；确定 Skill 的学习设计（九模块结构、来源硬性要求）——这是"我想要什么样的学习资料"的个人决策
2. **来源核查**：逐个点开每份资料末尾的参考来源链接，确认可访问、内容与资料中的引用一致
3. **内容核查与修改**：通读三份资料，核对概念表述与来源是否一致（如 Lost in the Middle 的 U 形结论、渐进式披露的三层 token 开销、Workflow/Agent 的分界），修正初稿中的错别字
4. **个人化改写**：三份资料中"我的解释"部分在 AI 初稿基础上改写为自己的表述（此节在提交前由本人复核）

> 人工核查的修改通过 Git 提交记录可追溯。

## 安全说明

- 本仓库不含 API Key、密码、令牌或个人隐私信息
- `.gitignore` 已配置排除 `.env`、密钥文件、凭据文件等敏感内容
- Git 提交使用 GitHub 隐私邮箱（noreply），不暴露真实邮箱

## 后续计划

用这个 Skill 继续学习后续课程概念（强化学习、RAG、多智能体协作……），让 `learning-materials/` 成长为个人概念知识库。
