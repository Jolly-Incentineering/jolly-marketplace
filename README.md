# jolly-marketplace

Jolly's internal Claude Code plugin marketplace. Add this once and install any Jolly plugin from it — more are added as workflows are built out.

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

This walks you through connecting your integrations, installs the deck workflow plugin for this project, and gets your workspace configured. Takes about 2 minutes.

Run `claude plugin marketplace update` to pick up newly added plugins.

---

## Available plugins

| Plugin | What it does | Install command |
|--------|-------------|-----------------|
| [`jolly-onboarding`](https://github.com/nishant-jolly/opportunity-analysis) | First-time setup — checks integrations, installs plugins, configures workspace | `/plugin install jolly-onboarding@nishant-jolly --scope user` |
| [`opportunity-analysis`](https://github.com/nishant-jolly/opportunity-analysis) | Research, model, and format a client Opportunity Analysis from start to finish | Installed automatically by `/jolly-onboarding` |

---

## Adding a new plugin

1. Create the plugin repo under `nishant-jolly/`
2. Add it to `.claude-plugin/marketplace.json` in this repo
3. Teammates run `claude plugin marketplace update` to pick up the new plugin
