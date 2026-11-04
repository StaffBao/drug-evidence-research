# Drug Evidence Research

A reusable, agent-agnostic skill for researching drug mechanisms, clinical trials, efficacy, safety, and regulatory or development status—with conclusions traced to primary sources.

Built from a detailed GLP-1 research project, the workflow can be applied to other therapeutic areas. It uses Markdown instructions and JSON templates, with no required runtime, package installation, or vendor-specific configuration.

## What it helps you do

- **Explain mechanisms clearly.** Connect source cells, molecular processing, receptors, target organs, normal physiology, and the point of drug intervention.
- **Reconstruct trial designs.** Identify each treatment arm, complete dosing schedules, comparators, background treatment, blinding, and follow-up periods.
- **Compare efficacy and safety responsibly.** Keep populations, endpoints, analysis sets, denominators, and time points visible. Separate direct comparisons from indirect evidence.
- **Interpret statistics in context.** Distinguish superiority, noninferiority, equivalence, exploratory findings, and unadjusted comparisons.
- **Assess formulation and route differences.** Separate administered dose, bioavailability, systemic exposure, clinical outcomes, bioequivalence, and regulatory bridging.
- **Track what has actually changed.** Distinguish trial results, company plans, regulatory decisions, and study-registration status.
- **Turn evidence into readable outputs.** Use treatment-arm tables, mechanism explanations, reports, or slide content while preserving important qualifications and source links.

For example, it helps structure questions such as: Does low oral bioavailability imply greater toxicity? Does preserving lean mass demonstrate better physical function? Does a failed noninferiority endpoint mean development has stopped?

## Who it is for

Researchers, clinical-development and medical-affairs teams, pharmacovigilance professionals, pharmaceutical and biotech analysts, and students who need to read and explain drug evidence.

The skill supports research and communication. It does not provide individualized prescribing or switching decisions, and it does not guarantee access to full-text literature.

## Quick start

### Option 1: Use a chat assistant without installing a skill

Upload the [single-file edition](药物临床证据研究_单文件使用版.md), which includes the workflow, reference modules, and templates. Then send:

```text
Read the attached Drug Evidence Research single-file edition and apply its
methods to this question: [your question].

Treatments or formulations: [specify]
Population and region: [specify]
Evidence cutoff: [date]
Output: [short answer, comparison tables, report, or slide content]
Language: English

Cite primary sources for key claims. Distinguish direct comparisons,
indirect evidence, model estimates, and unresolved questions.
If a source or part of the attachment is inaccessible, state that limitation.
```

An assistant that cannot accept Markdown files may accept a `.txt` copy or pasted sections. Current-evidence research requires appropriate search and source-reading capabilities; supplied materials can also be analyzed offline.

### Option 2: Install the complete skill folder

Download and extract the sharing package, or copy the [`drug-evidence-research`](drug-evidence-research/) folder from this repository. Place the entire folder in one of the skill directories below.

| Agent | Project-level parent directory | Personal parent directory | How to start |
|---|---|---|---|
| Claude Code | `.claude/skills/` | `~/.claude/skills/` | `/drug-evidence-research`, followed by your question |
| Cursor | `.cursor/skills/` | `~/.cursor/skills/` | Type `/` in Agent chat and select the skill |
| VS Code Copilot | `.github/skills/` | `~/.copilot/skills/` | Select the skill from the chat `/` menu |
| Gemini CLI | `.gemini/skills/` | `~/.gemini/skills/` | Check `/skills list`, then ask to use the skill |
| OpenCode | `.opencode/skills/` | `~/.config/opencode/skills/` | Ask the agent to load and use `drug-evidence-research` |
| Codex | `.agents/skills/` | `~/.agents/skills/` | `$drug-evidence-research`, followed by your question |

These are **parent directories**. For example, a project installation for Claude Code should contain `.claude/skills/drug-evidence-research/SKILL.md`.

`~` means your home directory. On Windows, you can open it with `%USERPROFILE%` in File Explorer. Choose one installation location and preserve the folder structure. Reopen or refresh your session if the skill does not appear; Gemini CLI also provides `/skills reload`.

The instructions target versions that support these skill features. Directory and command guidance has been checked against product documentation; installations have not been tested individually in every product. Local files must also be made available in the actual execution environment when using cloud or remote sessions.

### Option 3: Load the files manually

If your agent can read project files but does not support skill installation, keep the folder in your project and ask:

```text
Read drug-evidence-research/SKILL.md and the reference files needed for
this task. Apply that workflow to: [your research question].
```

Adjust the path to match your project. Reading only the entry file is insufficient if the task requires reference modules the agent cannot access.

## How the workflow works

**Define the question → identify primary evidence → reconstruct the study → assess comparability → state supported conclusions and limits → present clearly.**

The workflow asks the agent to preserve the details that change interpretation: molecule and formulation, complete regimen, population, comparator, endpoint, analysis set, estimand, observation window, and source location.

It separates participant counts from event counts, serious adverse events from symptom severity, and absent reporting from explicitly reported zero events. It also keeps animal mechanisms, human observations, model predictions, and confirmed clinical findings distinct.

For a narrow question, a short answer with the necessary evidence is enough. A comprehensive report is used only when the task calls for one.

## Package contents

```text
drug-evidence-research/
├── SKILL.md
├── references/
│   ├── evidence-and-records.md
│   ├── trials-and-safety.md
│   ├── mechanisms-and-pk.md
│   ├── approvals-and-development.md
│   ├── presentation-and-updates.md
│   └── worked-example.md
└── assets/
    ├── research-record.template.json
    └── report-template.md
```

The [JSON research-record template](drug-evidence-research/assets/research-record.template.json) helps connect claims, sources, treatment arms, results, and status events. The [report template](drug-evidence-research/assets/report-template.md) provides an optional output structure. Use only the sections relevant to your question.

## Language and scope

This README is in English. The core instructions, reference modules, templates, and single-file edition are currently written in Chinese. You can request output in English or another language; the skill materials themselves have not been fully translated into English.

The package contains a research method, not a continuously updated drug database. Historical examples illustrate interpretation and should not be treated as current product guidance. Use an explicit evidence cutoff and verify current claims against the relevant sources.

## Sharing and adapting

Share `drug-evidence-research-v1.1.0-universal.zip` for the full package, or the single-file edition for an upload-based workflow. Preserve the complete skill folder when installing it.

For a first check, ask the agent to summarize the workflow it loaded and identify the reference modules it needs. Then verify that the answer states who was studied, what was given, what it was compared with, when outcomes were measured, and what the evidence can and cannot establish.

For Chinese installation instructions and example prompts, see [使用与分享](使用与分享.md).
