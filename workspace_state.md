# Shared Research Workspace State

> **SYSTEM RULE:** Every agent MUST read this file before starting a task and update its designated section upon completion. Do not alter another agent's locked section.

## 1. Project Metadata (Managed by Orchestrator)
* **Status:** `[INITIALIZED | IN_PROGRESS | RED_TEAM_REVIEW | MERGING | COMPLETED]`
* **Research Topic / Title:** `<TBD by Orchestrator>`
* **Core Research Question:** `<TBD by Orchestrator>`
* **Hypothesis:** `<TBD by Orchestrator>`
* **Target Citation Style:** `<e.g., APA 7th / IEEE>`
* **Target Word Count:** `<e.g., 4500 words>`

## 2. Standardized Terminology Glossary (Strict Enforcement)
* *All agents must use these exact terms to prevent drift:*
  * **Subjects/Users:** `<e.g., "study participants" (never "users" or "subjects")>`
  * **Primary Metric:** `<e.g., "task completion latency">`
  * **Tense Rules:** Past tense for Methodology & Results; Present tense for established facts & Discussion implications.

## 3. Master Citation Registry (Managed by `01_agent_literature`)
* *Format: `[CITE_KEY]` -> Full Reference*
  * `<CITE_KEY>`: `<Full verified reference in the selected citation style>`

## 4. Data & Figure Registry (Managed by `03_agent_analyst`)
* *Format: `[FIG_X]` or `[TAB_X]` -> Key statistical takeaway*
  * `[TAB_1]`: Demographic breakdown ($N = 120$).
  * `[FIG_1]`: Primary outcome comparison ($p < 0.01$).

## 5. Methodological Anomalies & Limitations Log (Managed by `02_agent_methodology`)
* *Notes passed directly to `04_agent_discussion_editor`:*
  * `<None logged yet>`

## 6. Red-Team Review Flags (Cross-Agent Audit)
* `[ ]` **Literature -> Intro Check:** Verify background framing is accurate.
* `[ ]` **Methodology -> Results Check:** Verify all planned variables in Methods are reported in Results.
* `[ ]` **Analyst -> Discussion Check:** Verify Discussion claims do not exaggerate statistical significance.
