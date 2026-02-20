# Jolly Marketplace

Jolly's internal Claude Code plugin marketplace. Add it once per machine and install any Jolly plugin from it.

---

## New teammate setup

**Step 1 — Add the marketplace (once per machine):**

```
/plugin marketplace add nishant-jolly/jolly-marketplace
```

**Step 2 — Install the Opportunity Analysis plugin:**

```
/plugin install opportunity-analysis@nishant-jolly --scope user
```

**Step 3 — Run first-time workspace setup:**

```
/deck-setup
```

This detects your Jolly folder, configures your workspace, and saves the settings. Run it once per machine.

Full setup guide → see **#7: Opportunity Analysis Plugin — Setup Guide** in the Incentineering section of Notion.

---

## Available plugins

| Plugin | What it does |
|--------|-------------|
| [`opportunity-analysis`](https://github.com/nishant-jolly/opportunity-analysis) | Research, model, and format a client Opportunity Analysis from start to finish. Run `/deck-help` inside Claude Code for a full command reference. |

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
