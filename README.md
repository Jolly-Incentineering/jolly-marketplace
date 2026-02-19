# jolly-marketplace

Jolly's internal Claude Code plugin marketplace. Add this once and you can install any Jolly plugin.

---

## Quick Install (new teammate setup)

Run these two commands in Claude Code — that's it:

```
claude plugin marketplace add https://github.com/nishant-jolly/jolly-marketplace
```
```
/plugin install opportunity-analysis@nishant-jolly
```

Then use `/deck-auto [Company]` to run the full workflow.

---

## Available plugins

| Plugin | What it does | Install command |
|--------|-------------|-----------------|
| `opportunity-analysis` | Research, model, and format a client Opportunity Analysis from start to finish | `/plugin install opportunity-analysis@nishant-jolly` |

---

## Workflow overview

```mermaid
flowchart TD
    AUTO["<b>/deck-auto [Company]</b><br/>Runs the entire flow below automatically<br/>Pauses only at gates and manual steps<br/>Saves progress after every phase"]
    AUTO -. "wraps" .-> SETUP

    SETUP["<b>/deck-setup</b><br/>One time per machine"] --> START

    START["<b>/deck-start [Company]</b><br/>Create folder, copy templates,<br/>add to Notion, download assets"] --> DETECT

    DETECT{"Branch detection<br/>Does prior data exist?"}

    DETECT -->|"Branch A — Existing client<br/>Gong calls + Attio + Slack data found"| RA
    DETECT -->|"Branch B — Cold prospect<br/>No prior data"| RB

    subgraph branchA ["Branch A — Existing Client"]
        RA["<b>/deck-research</b><br/>Attio + Gong calls<br/>Microsoft 365 emails<br/>Slack messages<br/>Public data<br/>All 4 run in parallel"]
        RA --> GA
        GA{{"Gate: Confirm<br/>campaign list"}}
        GA --> MA
        MA["<b>/deck-model</b><br/>Fill Excel model<br/>with research-backed values"]
        MA --> GB
        GB{{"Gate: Approve values<br/>before writing"}}
        GB --> FA
        FA["<b>/deck-format</b><br/>Apply brand assets<br/>Fill presentation with numbers<br/>Export PDF"]
        FA --> GC
        GC{{"Gate: 3 manual steps<br/>Macabacus refresh<br/>Figma frame placement<br/>Link-break in PowerPoint"}}
        GC --> QA_A
        QA_A["<b>/deck-qa</b><br/>Run 13 quality checks"]
        QA_A --> DA["Delivery-ready<br/>Opportunity Analysis"]
    end

    subgraph branchB ["Branch B — Cold Prospect"]
        RB["<b>/deck-research</b><br/>Public sources only<br/>SEC filings, web, LinkedIn"]
        RB --> GD
        GD{{"Gate: Confirm<br/>standard campaign list"}}
        GD --> MB
        MB["<b>/deck-model</b><br/>Fill Excel model<br/>with illustrative numbers"]
        MB --> GE
        GE{{"Gate: Approve values<br/>before writing"}}
        GE --> FB
        FB["<b>/deck-format</b><br/>Apply brand assets<br/>Fill presentation with numbers<br/>Export PDF"]
        FB --> QA_B
        QA_B["<b>/deck-qa</b><br/>Run 13 quality checks"]
        QA_B --> DB["Delivery-ready<br/>Opportunity Analysis"]
    end

    style AUTO fill:#f0f4ff,stroke:#4a6fa5,stroke-width:2px,color:#1a1a2e
    style DETECT fill:#fff8e1,stroke:#f0a500,stroke-width:2px
    style GA fill:#ffe0b2,stroke:#e65100,stroke-width:2px
    style GB fill:#ffe0b2,stroke:#e65100,stroke-width:2px
    style GC fill:#ffe0b2,stroke:#e65100,stroke-width:2px
    style GD fill:#ffe0b2,stroke:#e65100,stroke-width:2px
    style GE fill:#ffe0b2,stroke:#e65100,stroke-width:2px
    style DA fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    style DB fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
```

---

## Adding a new plugin

1. Create the plugin repo under `nishant-jolly/`
2. Add it to `.claude-plugin/marketplace.json` in this repo
3. Teammates run `claude plugin marketplace update` to pick up the new plugin
