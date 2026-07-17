# Prompt A/B Testing Platform

> Statistically rigorous prompt optimization.

Randomizes users to prompt variants, runs Bayesian posterior + sequential probability ratio test (SPRT), guards against Simpson's paradox, and auto-promotes winners.

**Part of [AEGIS](https://github.com/KnigguKniggu-droid/AEGIS)** — Adaptive AI Governance Infrastructure for Cyber-Physical Systems. This subsystem maps to **L5: Adaptive Control** (Sequential hypothesis testing (SPRT) — fixed-hash traffic splitting with Welch's t-test and Bonferroni correction.).

---

## Architecture Position

```
AEGIS Layer: L5: Adaptive Control
ECE Mapping: Sequential hypothesis testing (SPRT) — fixed-hash traffic splitting with Welch's t-test and Bonferroni correction.
```

This module is one of 15 subsystems in the AEGIS platform. See the [unified architecture](https://github.com/KnigguKniggu-droid/AEGIS#readme) for how all components interconnect.

---

## Features

- Randomized user-to-variant assignment with stratified randomization
- Bayesian posterior + SPRT for early stopping with confidence
- Simpson's paradox guards via stratified randomization
- Auto-promote winner; auto-rollback on regression detection
- Dashboard: posterior distributions, expected lift, sample size calculator

---

## Tech Stack

`Python` | `FastAPI` | `PostgreSQL` | `SciPy/NumPy` | `Streamlit` | `Celery` | `Redis`

---

## Quick Start

```bash
git clone https://github.com/KnigguKniggu-droid/09-prompt-ab-testing-platform.git
cd 09-prompt-ab-testing-platform
pip install -e .
```

Run tests:

```bash
pytest tests/ -v
```

---

## Project Structure

```
09_prompt_ab_testing_platform/
  src/                  # Core application code
  tests/                # 0 passing tests
  .github/              # CI/CD workflows
  Dockerfile            # Container build
  pyproject.toml        # Package configuration
```

---

## Running in Docker

```bash
docker build -t 09_prompt_ab_testing_platform .
docker run -p 8000:8000 09_prompt_ab_testing_platform
```

---

## ECE Design Principles

This subsystem is modeled after classical electrical and computer engineering concepts:

> **Sequential hypothesis testing (SPRT) — fixed-hash traffic splitting with Welch's t-test and Bonferroni correction.**

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
