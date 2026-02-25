# Jolly Marketplace

Jolly's internal Claude Code plugin marketplace. Add it once per machine and install any Jolly plugin from it.

---

## Quick Install (new teammate setup)

**Step 0 — Make sure Git is installed and configured for HTTPS:**

The plugin system uses Git to download plugins. If you don't have Git, Step 1 will fail.

*Check:* Open a terminal and run `git --version`. If you see a version number, skip to the HTTPS config below.

*Windows — install Git:*
Download from https://git-scm.com/download/win and run the installer (use all default settings).

*Mac — install Git:*
Run `xcode-select --install` in Terminal. Click Install when the dialog appears (~2–5 min).

*Then configure Git to use HTTPS (both platforms):*
```
git config --global url."https://github.com/".insteadOf git@github.com:
```
This prevents "Permission denied (publickey)" errors. On Windows, the credential manager handles GitHub login automatically. On Mac, you'll be prompted for your GitHub username and a personal access token (create one at https://github.com/settings/tokens with "repo" scope).

**Step 1 — Add the marketplace once per machine:**

```
/plugin marketplace add Jolly-Incentineering/jolly-marketplace
```

**Step 2 — Install the opportunity-analysis plugin (available everywhere):**

```
/plugin install opportunity-analysis@Jolly-Incentineering --scope user
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

### opportunity-analysis (v2.2.0)
**What it does:** Build a complete client Opportunity Analysis from start to finish using the Intro Deck template. Handles research (CRM, Slack, Gong, public data), financial modeling, PowerPoint formatting, and quality assurance automatically. Just provide the company name and approve at each gate. New in v2.2.0: Inbox Feed Generator auto-creates branded push notification copy for Figma, scripts optimized for speed, and Brandfetch/Goody tools now support direct CLI automation.

**Includes:** The `/jolly-onboarding` skill for first-time setup is bundled inside this plugin.

**Context-based workflow:** Pre-call uses Slack + Public data (~8–12 min). Post-call includes full Attio/Gong research with transcripts (~14–20 min).

**How to install:**
```
/plugin install opportunity-analysis@Jolly-Incentineering --scope user
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
/plugin update opportunity-analysis@Jolly-Incentineering
```

---

## Adding a new plugin (ops)

1. Create the plugin repo under `Jolly-Incentineering/`
2. Add it to `.claude-plugin/marketplace.json` in this repo
3. Teammates run `/plugin marketplace update` to pick up the new plugin
