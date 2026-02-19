# jolly-marketplace

Jolly's internal Claude Code plugin marketplace. Add this once and install any Jolly plugin from it — more are added as workflows are built out.

---

## Quick Install (new teammate setup)

Add the marketplace once per machine:

```
/plugin marketplace add nishant-jolly/jolly-marketplace
```

Then install whichever plugins you need. Run this from inside your Jolly - Documents folder:

```
/plugin install opportunity-analysis@nishant-jolly --scope local
```

Run `claude plugin marketplace update` to pick up newly added plugins.

---

## Available plugins

| Plugin | What it does | Install command |
|--------|-------------|-----------------|
| [`opportunity-analysis`](https://github.com/nishant-jolly/opportunity-analysis) | Research, model, and format a client Opportunity Analysis from start to finish | `/plugin install opportunity-analysis@nishant-jolly` |

---

## Adding a new plugin

1. Create the plugin repo under `nishant-jolly/`
2. Add it to `.claude-plugin/marketplace.json` in this repo
3. Teammates run `claude plugin marketplace update` to pick up the new plugin
