# Claude Prompt — AgentShield Phase 0 Independent Review

You are acting as a critical senior software architect, application-security reviewer, and academic project mentor.

I am building a solo 5-credit final-year project:

**AgentShield: A Machine Learning–Driven Security and Reliability Framework for Tool-Using AI Agents**

I will provide the Phase 0 project documents:
- THREAT_MODEL.md
- SCENARIO_SPECIFICATION.md
- PROJECT_REQUIREMENTS.md
- EXPERIMENT_PROTOCOL.md
- DEVELOPMENT_RULES.md
- phase0_scenarios.jsonl

## Your task

Review these documents as a coherent project specification. Do not rewrite the project into a different idea and do not add scope casually.

### Fixed architecture

M1 simulated deterministic agent; M2 input validation and normalization; M3 rule-based + TF-IDF/Logistic Regression threat detector; M4 YAML policy and authorization engine with ALLOW/BLOCK/REQUIRE_APPROVAL; M5 secure tool execution; M6 local simulated Web Fetch, Restricted File Reader, SQLite DB Tool; M7 output inspection and data protection; M8 reliability/loop monitor; M9 SQLite audit logging; M10 Streamlit dashboard; M11 experiment runner.

### Fixed constraints

- Solo student, 12-week target.
- Free/open-source, local-first, CPU-friendly.
- No paid APIs, cloud dependency, GPU, real credentials, or real personal data.
- Simulated web pages only; no real internet fetch.
- A deterministic scripted agent is the initial implementation; optional local LLM is a stretch goal only.
- The agent must consume fetched page output before selecting its next action, so indirect prompt-injection tests are meaningful.
- M3 detection is not authorization. M4 decides; M5 enforces.
- The protected tools must not be directly accessible by the agent outside the gateway.
- The benchmark compares unprotected, rules-only, and full modes using the same scenario suite.
- Use only synthetic secrets and isolated local fixtures.

## Review questions

1. Are there contradictions, ambiguous requirements, missing interfaces, or circular dependencies?
2. Is the threat model realistic for the stated prototype? What is missing or incorrectly scoped?
3. Are the three experiment modes defined fairly and safely?
4. Are attack success, prevention, false-positive, benign completion, latency, and loop metrics operationally defined well enough?
5. Does the scenario schema support reproducibility and avoid train/test leakage?
6. Is the 12-week scope feasible for one student? Identify the highest-risk features.
7. What acceptance tests must exist to prove denied actions never execute?
8. What is the minimum viable implementation order that preserves the architecture?
9. What claims should the final report avoid making?
10. What should be confirmed with the VIT project mentor before implementation?

## Output format

Return:
A. Critical issues (ranked by severity)
B. Specific corrections (document name + exact section + proposed wording)
C. Missing acceptance tests
D. Scope risks and cuts that do not damage the core research question
E. A concise mentor-review checklist
F. Final verdict: ready to start Phase 1, or not yet ready

Be strict and specific. Do not invent experimental results. Do not claim the system can universally prevent prompt injection. Do not add MCP, Docker, multi-agent orchestration, cloud deployment, or more tools unless you can justify why they are essential.

If a requirement is underspecified, flag it rather than silently assuming an answer.
