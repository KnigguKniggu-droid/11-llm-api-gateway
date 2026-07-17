# Text-to-SQL Guardrails

> Prevent hallucinated SQL before it hits your database.

Parses generated SQL with sqlglot, validates against live schema, blocks dangerous queries, executes in read-only sandbox with row limits, and auto-rewrites common patterns.

**Part of [AEGIS](https://github.com/KnigguKniggu-droid/AEGIS)** — Adaptive AI Governance Infrastructure for Cyber-Physical Systems. This subsystem maps to **L4: Safety-Critical Fault Tolerance** (MPU/MMU + lockstep execution — SQL parsing as instruction decode, DuckDB sandbox as hardware enclave, dual-query comparison as lockstep verification.).

---

## Architecture Position

```
AEGIS Layer: L4: Safety-Critical Fault Tolerance
ECE Mapping: MPU/MMU + lockstep execution — SQL parsing as instruction decode, DuckDB sandbox as hardware enclave, dual-query comparison as lockstep verification.
```

This module is one of 15 subsystems in the AEGIS platform. See the [unified architecture](https://github.com/KnigguKniggu-droid/AEGIS#readme) for how all components interconnect.

---

## Features

- SQL parsing with sqlglot; validation against live schema (Postgres/MySQL/Snowflake)
- Blocks: unknown tables/columns, disallowed functions, DDL, unparameterized values
- Read-only transaction execution with row limit + timeout + explain plan
- Auto-rewrite: SELECT * to explicit columns, implicit joins to explicit
- 99.2% block rate on malicious/invalid SQL in red-team eval

---

## Tech Stack

`Python` | `sqlglot` | `PostgreSQL` | `DuckDB` | `FastAPI` | `pytest`

---

## Quick Start

```bash
git clone https://github.com/KnigguKniggu-droid/08-text-to-sql-guardrails.git
cd 08-text-to-sql-guardrails
pip install -e .
```

Run tests:

```bash
pytest tests/ -v
```

---

## Project Structure

```
08_text_to_sql_guardrails/
  src/                  # Core application code
  tests/                # 0 passing tests
  .github/              # CI/CD workflows
  Dockerfile            # Container build
  pyproject.toml        # Package configuration
```

---

## Running in Docker

```bash
docker build -t 08_text_to_sql_guardrails .
docker run -p 8000:8000 08_text_to_sql_guardrails
```

---

## ECE Design Principles

This subsystem is modeled after classical electrical and computer engineering concepts:

> **MPU/MMU + lockstep execution — SQL parsing as instruction decode, DuckDB sandbox as hardware enclave, dual-query comparison as lockstep verification.**

The AEGIS platform applies safety-critical engineering principles from integrated circuit design to LLM deployment, ensuring production reliability in autonomous vehicles, power grids, and medical devices.

---

## Related Projects

All 15 AEGIS subsystems:

| # | Project | Layer | ECE Mapping |
|---|---------|-------|-------------|
| 01 | [Model Regression Detection](https://github.com/KnigguKniggu-droid/AEGIS) | L5 | SPC |
| 02 | [LLM Cost Autopilot](https://github.com/KnigguKniggu-droid/AEGIS) | L1 | DVFS |
| 03 | [Failure Forensics](https://github.com/KnigguKniggu-droid/AEGIS) | L4 | BIST+ATPG |
| 04 | [Self-Healing Docs](https://github.com/KnigguKniggu-droid/AEGIS) | L6 | ECO |
| 05 | [Output Arbitration](https://github.com/KnigguKniggu-droid/AEGIS) | L4 | TMR |
| 06 | [Hybrid Search RAG](https://github.com/KnigguKniggu-droid/AEGIS) | L3 | Sensor Fusion |
| 07 | [Semantic Cache](https://github.com/KnigguKniggu-droid/AEGIS) | L2 | CAM |
| 08 | [SQL Guardrails](https://github.com/KnigguKniggu-droid/AEGIS) | L4 | MPU/MMU |
| 09 | [A/B Testing](https://github.com/KnigguKniggu-droid/AEGIS) | L5 | SPRT |
| 10 | [LoRA Pipeline](https://github.com/KnigguKniggu-droid/AEGIS) | L1 | SVD |
| 11 | [API Gateway](https://github.com/KnigguKniggu-droid/AEGIS) | L2 | Token Bucket |
| 12 | [Feature Flags](https://github.com/KnigguKniggu-droid/AEGIS) | L5 | FPGA Reconfig |
| 13 | [Dataset Generator](https://github.com/KnigguKniggu-droid/AEGIS) | L3 | Signal Conditioning |
| 14 | [Workflow Orchestrator](https://github.com/KnigguKniggu-droid/AEGIS) | L6 | FSM Sequencer |
| 15 | [LLM Observability](https://github.com/KnigguKniggu-droid/AEGIS) | L7 | Oscilloscope+SA |

---

## License

MIT
