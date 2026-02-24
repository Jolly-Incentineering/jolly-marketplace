# Jolly Marketplace

Jolly's internal Claude Code plugin marketplace. Add it once per machine and install any Jolly plugin from it.

---

## Quick Install (new teammate setup)

**Step 1 — Add the marketplace once per machine:**

```
/plugin marketplace add nishant-jolly/jolly-marketplace
```

**Step 2 — Install the opportunity-analysis plugin (available everywhere):**

```
/plugin install opportunity-analysis@nishant-jolly --scope user
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

### opportunity-analysis (v2.0.1)
**What it does:** Build a complete client Opportunity Analysis from start to finish using the Quick Deck template. Handles research (CRM, Slack, Gong, public data), financial modeling, PowerPoint formatting, and quality assurance automatically. Just provide the company name and approve at each gate.

**Includes:** The `/jolly-onboarding` skill for first-time setup is bundled inside this plugin.

**Context-based workflow:** Pre-call uses Slack + Public data (~8–12 min). Post-call includes full Attio/Gong research with transcripts (~14–20 min).

**How to install:**
```
/plugin install opportunity-analysis@nishant-jolly --scope user
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
/plugin update opportunity-analysis@nishant-jolly
```

---

## Adding a new plugin (ops)

1. Create the plugin repo under `nishant-jolly/`
2. Add it to `.claude-plugin/marketplace.json` in this repo
3. Teammates run `/plugin marketplace update` to pick up the new plugin
