# Jolly Marketplace

Jolly's internal Claude Code plugin marketplace. Add it once per machine and install any Jolly plugin from it.

---

## Quick Install (new teammate setup)

**Step 1 — Add the marketplace once per machine:**

```
/plugin marketplace add nishant-jolly/jolly-marketplace
```

**Step 2 — Install the onboarding guide (available everywhere):**

```
/plugin install jolly-onboarding@nishant-jolly --scope user
```

**Step 3 — Open your Jolly - Documents folder in Claude Code, then run:**

```
/jolly-onboarding
```

This walks you through in plain language:
- Connecting Slack and Attio integrations (takes 5 minutes)
- Setting your JOLLY_WORKSPACE environment variable (Windows or Mac specific)
- Running the one-time workspace setup

When you're done, you're ready to run `/deck-auto [Company Name]` for your first opportunity analysis.

**Total time:** ~10 minutes. One-time setup per machine.

Run `claude plugin marketplace update` to pick up newly added plugins.

---

## Available plugins

### jolly-onboarding (v1.0.15)
**What it does:** First-time setup guide for new teammates. Walks through connecting Slack, configuring environment variables, connecting Attio, and running the one-time workspace setup. No technical knowledge required.

**How to install:**
```
/plugin install jolly-onboarding@nishant-jolly --scope user
```

Then run:
```
/jolly-onboarding
```

---

### opportunity-analysis (v1.0.15)
**What it does:** Build a complete client Opportunity Analysis from start to finish. Two deck types:
- **With Commentary** (~20–25 min): After a call. Includes narrative, talking points, and full internal data. 13 QA checks.
- **Without Commentary** (~10–15 min): Before a call. Numbers only, cold outreach. Streamlined 11 QA checks.

Handles research (CRM, Slack, Gong, public data), financial modeling, PowerPoint formatting, and quality assurance automatically. Just provide the company name and approve at each gate.

**How to install:** Installed automatically when you run `/jolly-onboarding`, or manually with:
```
/plugin install nishant-jolly/opportunity-analysis --scope user
```

**Quick start:**
```
/deck-auto [Company Name]
```

Example: `/deck-auto Firebirds`

---

## Commands

Once the plugin is installed, these slash commands are available in Claude Code:

| Command | What it does |
|---------|-------------|
| `/deck-help` | Show a full quick-reference guide for all commands |
| `/deck-setup` | One-time workspace setup — run once per machine |
| `/deck-auto [Company]` | Run the full Opportunity Analysis workflow automatically |
| `/deck-start [Company]` | Step 1: create folders, copy templates, open files |
| `/deck-research` | Step 2: research the company across all sources |
| `/deck-model` | Step 3: populate the Excel model |
| `/deck-format` | Step 4: format the PowerPoint and export PDF |
| `/deck-qa` | Step 5: run quality checks before delivery |

---

## Updating

To pick up new plugin versions:

```
/plugin update opportunity-analysis
```

---

## Adding a new plugin (ops)

1. Create the plugin repo under `nishant-jolly/`
2. Add it to `.claude-plugin/marketplace.json` in this repo
3. Teammates run `/plugin marketplace update` to pick up the new plugin
