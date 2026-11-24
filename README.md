# Professor

Professor is a vendor-agnostic, multi-agent research workflow for producing careful academic papers. It organizes an orchestrator and four specialist roles around one shared project record, so research questions, terminology, methods, evidence, citations, and editorial decisions stay aligned from outline to final manuscript.

## Purpose

The system helps researchers move through a repeatable paper-writing process: define the research question, establish a literature context, design or document methods, analyze supplied evidence, discuss findings with appropriate limits, and assemble a polished manuscript. Its role prompts separate responsibilities and include review checks to reduce unsupported claims, inconsistent terminology, selective reporting, and fabricated data or citations.

Professor is an instruction and workflow scaffold. It does not itself provide research data, guarantee citation verification, or automatically run child agents; the active runtime follows `AGENTS.md` and uses its available delegation capabilities. If no empirical dataset is supplied, the workflow should explicitly use a systematic review, theoretical framework, or proposed protocol scope.

## Team

- **Orchestrator (`00_orchestrator`)** coordinates the workflow, maintains project metadata, creates the outline, performs framing, compiles the manuscript, and manages review.
- **Literature specialist (`01_agent_literature`)** synthesizes themes and maintains the verified citation registry.
- **Methodology architect (`02_agent_methodology`)** documents a reproducible study design and logs limitations.
- **Analyst (`03_agent_analyst`)** reports findings from supplied data without interpretation and maintains the table and figure registry.
- **Discussion editor (`04_agent_discussion_editor`)** interprets results in context, addresses limitations, and polishes the final manuscript.

## How it works

1. Read `AGENTS.md`, the shared state, and the relevant role prompts.
2. Supply a research topic, citation style, scope, and any dataset or source material.
3. Initialize metadata and terminology, then create a shared outline.
4. Draft literature and methodology, analyze evidence, and write the discussion in dependency order.
5. Run cross-agent checks for missing variables and overclaimed interpretations.
6. Compile and polish the manuscript in `outputs/FINAL_MANUSCRIPT.md`.

The orchestrator may run the literature and methodology roles concurrently when isolated workers are available. In a single-thread runtime, it switches roles sequentially while following each role's prompt.

## Repository layout

```text
Professor/
├── AGENTS.md                  # Universal bootstrap and execution instructions
├── README.md                  # Purpose, roles, and workflow overview
├── workspace_state.md         # Shared metadata, glossary, evidence registries, and review flags
├── prompts/                   # Orchestrator and four specialist role definitions
└── outputs/                   # Runtime-generated outline, sections, and final manuscript
```

Expected runtime outputs are `01_skeleton_outline.md`, `02_literature_review.md`, `03_methodology.md`, `04_results.md`, `05_discussion.md`, and `FINAL_MANUSCRIPT.md` inside `outputs/`.

## Evidence standards

- Never invent data, statistics, results, or references.
- Use `[VERIFY_CITATION: Author/Topic]` when a source cannot be verified.
- Keep methodology and results in past tense, and distinguish reported findings from interpretation.
- Record every citation, table, figure, limitation, and review flag in its assigned section of `workspace_state.md`.
- Follow the role-specific word-count, terminology, and reporting rules in `prompts/`.

## Getting started

Open this folder in an AI runtime that can read repository instructions. Give it a research topic and the available data or review scope, then ask it to start the Professor workflow. The runtime should begin with Phase 1 in `AGENTS.md` and ask for any essential missing research inputs before drafting.
