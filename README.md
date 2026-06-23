# Research Cycle Skill for Codex

A closed-loop research workflow skill for [Codex](https://github.com/OpenAI/codex) — from literature survey to paper publication, with **multi-agent adversarial debate** for gap discovery and **Semantic Scholar API** for literature validation.

## Highlights

- **7-Phase Closed Loop**: Literature Survey → Innovation Design → Baseline Reproduction → Implementation → Experiment → Analysis & Iteration → Paper Writing
- **Multi-Agent Adversarial Gap Discovery**: Proposer / Reviewer / Evidence roles engage in structured debate to avoid self-deception
- **Semantic Scholar API Validation**: Quantify research gap size instead of relying on intuition
- **Two Selection Strategies**: *Borrow-and-Swap* (take top-venue framework, swap domain) and *Core-Upgrade* (replace a single core component in a classical model)
- **Structured Output**: Standardized templates and decision records for every phase

## When to Use

- Graduate student topic selection and proposal
- Finding publishable research gaps
- Designing theoretically grounded innovations
- Standardized experiment validation workflows
- Paper writing assistance

## Installation

### Option 1: Manual Install

Copy the `.codex/skills/research-cycle/` directory to your Codex skills path:

```bash
# Global install (recommended)
cp -r .codex/skills/research-cycle/ ~/.codex/skills/research-cycle/

# Or project-level install
mkdir -p your-project/.codex/skills/
cp -r .codex/skills/research-cycle/ your-project/.codex/skills/research-cycle/
```

### Option 2: Clone Repository

```bash
git clone https://github.com/kris-yun/research-cycle-skill.git
cp -r research-cycle-skill/.codex/skills/research-cycle/ ~/.codex/skills/
```

## Usage

Use any of the trigger phrases in Codex to activate this skill automatically:

```
research cycle, research workflow, literature survey, research brainstorming,
scientific brainstorming, research gap, find research gap, adversarial debate,
innovation design, experiment design, run experiments, paper writing,
do research, research process, scientific gap finder, multi-agent debate,
gap analysis, literature review, academic research
```

### Example Prompts

> Run a research cycle on UAV gas source localization, targeting IEEE Sensors Journal

> Launch multi-agent adversarial debate to find research gaps in [domain]

> Use Semantic Scholar to validate how many papers exist in the [keyword] direction

## Workflow

```
Phase 1: Literature Survey & Multi-Agent Adversarial Gap Discovery
  ├── 1a: Literature Search + Semantic Scholar Validation
  ├── 1b: Proposer / Reviewer / Evidence Adversarial Debate
  └── 1c: GO / REVISE / KILL Decision
Phase 2: Innovation Design (theoretically grounded + explainable)
Phase 3: Baseline Reproduction (official code + official parameters)
Phase 4: Innovation Implementation (minimal changes + modular toggle)
Phase 5: Experimental Validation (multiple runs + ablation + cross-dataset)
Phase 6: Analysis & Iteration → back to Phase 2
Phase 7: Paper Writing
```

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `S2_API_KEY` | Semantic Scholar API key for literature validation | Optional (works without key, higher quota with key) |

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

[MIT License](LICENSE)