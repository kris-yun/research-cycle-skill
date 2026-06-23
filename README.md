# Research Cycle Skill for Codex

通用科学研究闭环工作流 skill，适用于 [Codex](https://github.com/OpenAI/codex)。

从文献调研到论文发表的完整研究闭环，集成了 **多Agent对抗辩论** 和 **Semantic Scholar API 文献验证**。

## 核心特性

- **7阶段完整闭环**：文献调研 → 创新点设计 → Baseline复现 → 实现 → 实验 → 分析迭代 → 论文撰写
- **多Agent对抗Gap发现**：Proposer/Reviewer/Evidence 三角色对抗辩论，避免自欺欺人
- **Semantic Scholar API 验证**：量化判断研究Gap大小，不靠直觉
- **两种选题策略**：借船出海（顶会框架换场景）和 换芯升级（经典模型换核心模块）
- **结构化输出**：每个阶段有标准化模板和决策记录

## 适用场景

- 研究生选题和开题
- 找有发表价值的研究gap
- 设计有理论支撑的创新点
- 规范化实验验证流程
- 论文撰写辅助

## 安装

### 方式 1：手动安装

将 `.codex/skills/research-cycle/` 目录复制到你的 Codex skills 目录：

```bash
# 全局安装（推荐）
cp -r .codex/skills/research-cycle/ ~/.codex/skills/research-cycle/

# 或项目级安装
mkdir -p your-project/.codex/skills/
cp -r .codex/skills/research-cycle/ your-project/.codex/skills/research-cycle/
```

### 方式 2：Clone 仓库

```bash
git clone https://github.com/kris-yun/research-cycle-skill.git
cp -r research-cycle-skill/.codex/skills/research-cycle/ ~/.codex/skills/
```

## 使用方法

在 Codex 中直接使用触发词即可自动激活：

```
研究循环、research cycle、找选题、文献调研、research brainstorming、
科学头脑风暴、研究gap、找研究gap、对抗性辩论、创新点设计、实验设计、
跑实验、论文撰写、做研究、科研流程、帮我找创新点、怎么发论文、
scientific gap finder
```

### 示例对话

```
> 帮我做研究循环，方向是无人机气体溯源，目标IEEE Sensors Journal

> 启动多Agent对抗辩论，帮我找[领域]的研究gap

> 用Semantic Scholar验证[关键词]方向有多少论文，判断Gap大小
```

## 工作流程

```
Phase 1: 文献调研 & 多Agent对抗Gap发现
  ├── 1a: 文献搜索 + Semantic Scholar验证
  ├── 1b: Proposer/Reviewer/Evidence 对抗辩论
  └── 1c: GO/REVISE/KILL 决策
Phase 2: 创新点设计（理论支撑 + 可解释性）
Phase 3: Baseline复现（官方代码 + 官方参数）
Phase 4: 创新点实现（最小修改 + 模块化开关）
Phase 5: 实验验证（多次运行 + 消融 + 跨数据集）
Phase 6: 结果分析 → 回到Phase 2迭代
Phase 7: 论文撰写
```

## 环境变量

| 变量 | 说明 | 必需 |
|------|------|------|
| `S2_API_KEY` | Semantic Scholar API Key，用于文献验证 | 可选（无Key也可用，有Key配额更高） |

## 许可证

MIT License