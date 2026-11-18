# AgentShield

**AgentShield: A Machine Learning–Driven Security and Reliability Framework for Tool-Using AI Agents**

AgentShield is a local, research-oriented prototype that places a security and reliability gateway between a tool-using AI agent and a small set of controlled tools. It combines request validation, rule-based and ML-assisted threat assessment, policy enforcement, controlled execution, output inspection, reliability monitoring, audit logging, and experimental evaluation.

## Project constraints

- Solo implementation; 12-week target.
- No paid APIs, cloud dependency, GPU, or real credentials.
- All tools and attack scenarios run locally in an isolated test environment.
- Initial agent is deterministic and scripted. A local LLM integration is optional and must not be required for core functionality.
- The agent must consume tool outputs when deciding subsequent actions; otherwise indirect prompt-injection experiments are invalid.
- Detection is not enforcement: the policy engine decides, and the execution layer must prevent denied calls from reaching tools.

## Official architecture

1. M1 — Simulated agent (planner/reasoner)
2. M2 — Input validation and normalization
3. M3 — Threat detection engine (rules + TF-IDF + Logistic Regression)
4. M4 — Policy and authorization engine
5. M5 — Secure tool execution layer
6. M6 — Controlled tools: simulated Web Fetch, Restricted File Reader, SQLite DB Tool
7. M7 — Output inspection and data protection
8. M8 — Reliability and execution-loop monitor
9. M9 — SQLite audit logging
10. M10 — Streamlit dashboard
11. M11 — Experiment runner and evaluation

## Phase 0 documents

- `docs/THREAT_MODEL.md`
- `docs/SCENARIO_SPECIFICATION.md`
- `docs/PROJECT_REQUIREMENTS.md`
- `docs/EXPERIMENT_PROTOCOL.md`
- `docs/DEVELOPMENT_RULES.md`

Starter scenarios: `data/scenarios/phase0_scenarios.jsonl`

## Phase 0 status

These documents define the proposed scope and acceptance criteria. They are not evidence that the modules have been implemented or that any security claim has been experimentally validated.
