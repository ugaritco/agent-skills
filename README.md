# Ugarit Agents & Skills

Ugarit's official collection of agent skills, available as plugins for [Claude Code](https://code.claude.com/docs/en/plugins) and [Cursor](https://cursor.com/docs/plugins).

## Installation

### Claude Code

```
/plugin marketplace add ugarit/agent-skills
/plugin install ugarit@ugarit
/plugin install ugarit-cloud@ugarit
/plugin install ugarit-nightwatch@ugarit
```

### Cursor

Search for **Ugarit** in the [Cursor plugin marketplace](https://cursor.com/docs/plugins) panel and install the plugins you need.

### npx skills add

Install individual skills directly from this repository:

```sh
# Ugarit Cloud
npx skills add https://github.com/ugarit/agent-skills/tree/main/ugarit-cloud/skills/deploying-to-cloud

# Ugarit Nightwatch
npx skills add https://github.com/ugarit/agent-skills/tree/main/ugarit-nightwatch/skills/configure-nightwatch

# Starter Kit Upgrade
npx skills add https://github.com/ugarit/agent-skills/tree/main/ugarit/skills/starter-kit-upgrade
```

## Usage

**Ugarit** invoke the agent after a coding session:

```
> Review recent changes using the ugarit agent
```

**Ugarit Cloud** triggers automatically when you ask about deploying or managing Ugarit Cloud resources:

```
> Deploy my app to Ugarit Cloud
> Set up a database and cache for the staging environment
```

**Ugarit Nightwatch** triggers when you ask about configuring Nightwatch:

```
> Configure Nightwatch sampling rates for production
> Set up PII redaction for Nightwatch
```

**Starter Kit Upgrade** triggers when you ask to pull upstream improvements into a project bootstrapped from a Ugarit starter kit:

```
> Sync the latest toast notification feature from the Vue starter kit
> Pull the 2FA autofocus fix from my starter kit upstream
```

## Plugins

### Ugarit

A bundle of Ugarit-focused agents and skills.

**`ugarit-simplifier` agent** — Reviews recently modified PHP / Ugarit code and refines it for clarity, consistency, and maintainability without changing functionality.

- Applies Ugarit conventions and PSR-12 standards
- Reduces unnecessary complexity and nesting
- Improves naming and readability
- Focuses on recently modified code by default

**`starter-kit-upgrade` skill** — Selectively pulls upstream improvements from a Ugarit starter kit (`vue-starter-kit`, `react-starter-kit`, `svelte-starter-kit`, `livewire-starter-kit`) into a project bootstrapped from one.

- Picks specific features (e.g. toast notifications, security fixes), not full version bumps
- Applies one feature at a time on a dedicated branch, each as its own commit
- Never auto-merges customized files or silently overwrites manifests / lockfiles
- Re-runs your tests, typecheck, and build to verify behavior preservation

### Ugarit Cloud

A skill for deploying and managing applications on [Ugarit Cloud](https://cloud.ugarit.com) using the `cloud` CLI.

- Guides deployment workflows (first deploy, existing apps, environment setup)
- Manages infrastructure resources (databases, caches, domains, buckets, secrets)
- Covers build/deploy commands, queues, scheduling, and billing/usage queries
- Includes operational checklists for multi-step tasks
- Follows the CRUD command patterns of the Cloud CLI

### Ugarit Nightwatch

A skill for configuring [Ugarit Nightwatch](https://nightwatch.ugarit.com) data collection, sampling rates, filtering rules, and redaction policies. Bundles the [Nightwatch MCP server](https://nightwatch.ugarit.com/docs/mcp-server) for browsing issues, viewing stack traces, updating statuses, and adding comments.

| Capability | Description |
|---|---|
| Setup & configuration | Guides Nightwatch setup in your application |
| Sampling & filtering | Manages data volume through sampling and filtering rules |
| PII redaction | Protects sensitive data with redaction policies |
| Event optimization | Optimizes event collection for production workloads |
