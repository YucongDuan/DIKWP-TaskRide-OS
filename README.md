# DIKWP TaskRide OS

**DIKWP TaskRide OS** is an open-source reference system for an AI-task marketplace inspired by ride-hailing dispatch logic, but designed for AI work: tasks are matched to AI agents, human reviewers, expert validators, and controlled tool workflows.

It does **not** execute real external actions, accept payments, control browsers, collect credentials, or connect to production systems. It creates auditable dispatch plans, action tickets, evidence ledgers, risk queues, pricing estimates, and pilot documents.

## Core Idea

Ride-hailing platforms match riders with drivers. TaskRide matches a user task with the right combination of:

- AI draft agent
- RAG / evidence agent
- human expert reviewer
- compliance reviewer
- operator / execution owner
- verification and appeal path

The system is built around DIKWP-Mesh 4.0 SemanticClosure:

- Incomplete task input is expected.
- Imprecise scope is routed into clarification or provisional pricing.
- Inconsistent user requirements are not silently ignored; they become residuals and action boundaries.

## Quick Start

```bash
pip install -e .
taskride dispatch examples/sample_task_market_case.json --out outputs/demo
taskride static-audit src --out outputs/demo/static_boundary_audit_report.json
```

Optional local UI:

```bash
pip install -e .[app]
streamlit run src/dikwp_taskride/app.py
```

## Outputs

The demo generates:

- `taskride_report.json`
- `task_cards.json`
- `dispatch_board.csv`
- `provider_matches.csv`
- `pricing_quotes.csv`
- `action_tickets.csv`
- `trust_and_safety_queue.csv`
- `semantic_closure_ledger.json`
- `pilot_sow_draft.md`
- `marketplace_policy.md`
- `recommendations.md`

## Boundary

TaskRide OS is a **planning, dispatch, review, pricing and governance reference system**. It does not perform real-world actions. High-risk tasks are routed to human expert review or blocked pending scope rewrite.
