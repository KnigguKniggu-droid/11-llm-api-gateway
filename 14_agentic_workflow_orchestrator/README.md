# Agentic Workflow Orchestrator

> Orchestrate multi-agent LLM workflows with state machines.

Temporal.io for durable execution, visual workflow designer, saga pattern with compensation rollback, human-in-the-loop checkpoints with approval flows.

**Part of [AEGIS](https://github.com/KnigguKniggu-droid/AEGIS)** — Adaptive AI Governance Infrastructure for Cyber-Physical Systems. This subsystem maps to **L6: Microcode Sequencer** (FSM microcode sequencer — planner/executor FSM with checkpoint persistence, saga compensation, temperature annealing on retry.).

---

## Architecture Position

```
AEGIS Layer: L6: Microcode Sequencer
ECE Mapping: FSM microcode sequencer — planner/executor FSM with checkpoint persistence, saga compensation, temperature annealing on retry.
```

This module is one of 15 subsystems in the AEGIS platform. See the [unified architecture](https://github.com/KnigguKniggu-droid/AEGIS#readme) for how all components interconnect.

---

## Features

- Temporal.io for durable execution; PostgreSQL for state
- Visual workflow designer via Streamlit (drag-drop nodes, define transitions)
- Built-in saga pattern: compensation transactions for rollback
- Human-in-the-loop checkpoints with Slack/email approval
- Retry policies, timeouts, heartbeats per activity

---

## Tech Stack

`Python` | `Temporal` | `PostgreSQL` | `Saga Pattern` | `Multi-Agent` | `Human-in-the-Loop` | `Streamlit`

---

## Quick Start

```bash
git clone https://github.com/KnigguKniggu-droid/14-agentic-workflow-orchestrator.git
cd 14-agentic-workflow-orchestrator
pip install -e .
```

Run tests:

```bash
pytest tests/ -v
```

---

## Project Structure

```
14_agentic_workflow_orchestrator/
  src/                  # Core application code
  tests/                # 32 passing tests
  .github/              # CI/CD workflows
  Dockerfile            # Container build
  pyproject.toml        # Package configuration
```

---

## Running in Docker

```bash
docker build -t 14_agentic_workflow_orchestrator .
docker run -p 8000:8000 14_agentic_workflow_orchestrator
```

---

## ECE Design Principles

This subsystem is modeled after classical electrical and computer engineering concepts:

> **FSM microcode sequencer — planner/executor FSM with checkpoint persistence, saga compensation, temperature annealing on retry.**

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
