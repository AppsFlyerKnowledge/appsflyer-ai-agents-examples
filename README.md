# appsflyer-ai-agents-examples

A curated collection of AI agent examples built on the **AppsFlyer MCP** — ready-to-use workflows and starter kits for performance marketers and growth teams.

## What this repo is

Each example shows how to connect an AI agent to AppsFlyer data via the AppsFlyer MCP and automate a real performance marketing task. Examples are organized by the agent platform they target.

## Repo structure

```
appsflyer-ai-agents-examples/
├── README.md                          ← You are here
├── Claude/                            ← Examples for Claude (Anthropic) + Cowork
│   └── AppsFlyer Cowork Starter Kit/  ← Full onboarding kit for Cowork users
│       ├── README.md                  ← Human-facing setup guide (screenshots, steps)
│       └── appsflyer-cowork-starter-kit.zip  ← Distributable deliverable
└── n8n/                               ← Examples for n8n automation workflows
    ├── caps_alert/                    ← Media spend cap alarm agent
    │   ├── README.md
    │   └── Media Spend Cap Alarm Agent.json
    └── executive_summary/             ← Executive summary email agent
        ├── README.md
        └── executive_summary_agent_gmail.json
```

## Examples

### Claude — AppsFlyer Cowork Starter Kit

**Location:** `Claude/AppsFlyer Cowork Starter Kit/`

A drop-in starter kit that takes an AppsFlyer customer from a fresh Cowork project to four running agents in under five minutes. Targets performance marketers with no prior AI/agent experience.

The kit covers four use cases with equal parity — no hero use case:
- Campaign Performance Analysis
- Cohort & Retention Analysis
- Automated Reporting
- Events Alarms

**Deliverable:** `appsflyer-cowork-starter-kit.zip` — the zip customers download and open directly in Cowork. Its contents are the source of truth; do not edit the zip directly.

**`README.md` in this folder** is the customer-facing setup guide (how to download, unzip, open in Cowork). It is not agent instructions.

**Inside the zip**, the key files for agents are:
- `CLAUDE.md` — the agent's operating instructions; governs every behavior in the session
- `questionnaire/onboarding.md` — the config questionnaire the agent runs on first open
- `agents/` — one `.md` file per use case; each defines the full agent flow
- `config.md` — written at runtime by the agent, stores user answers from the questionnaire
- `examples/` — sample outputs shown to users after an agent runs

### n8n — Caps Alert

**Location:** `n8n/caps_alert/`

An n8n workflow that monitors AppsFlyer cost data and fires an alert when media spend approaches or exceeds a defined cap. Import the JSON into any n8n instance.

### n8n — Executive Summary

**Location:** `n8n/executive_summary/`

An n8n workflow that generates a scheduled performance marketing executive summary and delivers it via Gmail. Import the JSON into any n8n instance.

## Conventions

- Every example lives in its own subfolder with a `README.md` that explains what it does and how to use it.
- Claude/Cowork examples include a `CLAUDE.md` (or one inside the zip) that contains the agent's operating instructions. These are read by the Claude agent at runtime — keep them accurate and up to date.
- n8n examples ship as a single importable `.json` workflow file alongside a `README.md`.
- `images/` subfolders contain screenshots used in the human-facing README. Do not reference them from agent instruction files.

## Adding a new example

1. Create a new subfolder under the appropriate platform directory (`Claude/` or `n8n/`).
2. Add a `README.md` describing the use case, prerequisites, and setup steps.
3. For Claude/Cowork examples: include a `CLAUDE.md` with the agent's operating instructions and a deliverable zip if applicable.
4. For n8n examples: include the exported workflow JSON.
5. Update this root `README.md` to list the new example under its platform.

## Prerequisites (all examples)

All examples require the **AppsFlyer MCP** to be connected and authenticated. Authentication is via OAuth — no API tokens to copy. See the relevant example's `README.md` or `PREREQUISITES.md` for the connection steps.

The core MCP tool used by most examples is `fetch_aggregated_data`. The AppsFlyer MCP is rate-limited to **20 calls/minute and 200 calls/day per user** — agent instructions are designed to stay within this budget.

## Notes & Disclaimer

These examples are provided as-is for educational and exploratory purposes. They include raw prompt structures and workflows designed to help you get started; they do not include pre-configured credentials, live data connections, or production-ready logic.

**What's included:**

- Starter prompt templates and workflows for building AppsFlyer-powered agents
- Documented placeholders for your own app IDs and configurations

**What's not included:**

- AppsFlyer credentials or account access
- Guarantees of output accuracy for any specific use case — results are based on your data
- Support for customizations made beyond these examples

By downloading and using these examples, you take responsibility for their implementation, configuration, and deployment in your environment. AppsFlyer provides these as a starting point; the outcomes depend on your data, your setup, and your decisions. We encourage you to test thoroughly before deploying any workflow. These are not intended to be used in a production environment.
