# Minimalist Monospace GitHub Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build and automate a high-signal, dark minimalist monospace GitHub Profile README for `0xrizz` with custom ASCII branding, curated typography, dark telemetry cards, a GitHub Action for dynamic recent activity, and an interactive CTA box.

**Architecture:** Create `README.md` with structured monospace sections (ASCII Hero, YAML Spec Sheet, Categorized Arsenal, Dark Minimalist Telemetry, Recent Activity container, Terminal CTA box) and `.github/workflows/update-activity.yml` to automatically fetch and update recent activity via GitHub Actions cron.

**Tech Stack:** Markdown, GitHub Actions, `jamesgeorge007/github-activity-readme`, `github-readme-stats`, `ascii-art` generator.

**Spec:** [`docs/superpowers/specs/2026-08-20-profile-readme-design.md`](file:///home/rizz/dev/0xrizz/docs/superpowers/specs/2026-08-20-profile-readme-design.md)

## Global Constraints

- **Aesthetic**: Pure dark minimalist / monospace terminal aesthetic (no default multi-color badges).
- **Color Scheme**: Obsidian Dark (`#0d1117`), Muted Silver/Gray (`#8b949e`), Crisp Accent (`#f0f6fc` / `#58a6ff`).
- **Dynamic Content**: Preserves `<!--START_SECTION:activity-->` and `<!--END_SECTION:activity-->` tags.
- **Workflow Security**: Grants explicit `contents: write` permission to the GitHub Actions job.

---

### Task 1: Generate & Construct `README.md`

**Files:**
- Create/Modify: `README.md`

**Interfaces:**
- Produces: Complete markdown structure containing the ASCII logo, metadata block, telemetry cards, activity hooks, and CTA terminal box.

- [ ] **Step 1: Write `README.md` with full Minimalist Monospace content**

```markdown
<div align="center">

<pre style="font-size: 11px; line-height: 1.15; font-family: monospace;">
 ██████╗   ██╗  ██╗  ██████╗   ██╗  ███████╗  ███████╗
██╔═████╗  ╚██╗██╔╝  ██╔══██╗  ██║  ╚══███╔╝  ╚══███╔╝
██║██╔██║   ╚███╔╝   ██████╔╝  ██║    ███╔╝     ███╔╝ 
████╔╝██║   ██╔██╗   ██╔══██╗  ██║   ███╔╝     ███╔╝  
╚██████╔╝  ██╔╝ ██╗  ██║  ██║  ██║  ███████╗  ███████╗
 ╚═════╝   ╚═╝  ╚═╝  ╚═╝  ╚═╝  ╚═╝  ╚══════╝  ╚══════╝
</pre>

`[ status: active ] • [ role: systems_and_ai_engineer ] • [ env: linux/x86_64 ]`

</div>

---

### 📋 Spec Sheet

```yaml
user: 0xrizz
focus:
  - distributed_systems
  - cloud_infrastructure
  - autonomous_ai_workflows
  - low_level_performance
principles:
  - high_signal_low_noise
  - architecture_first
  - clean_pragmatic_engineering
```

---

### 🛠️ Technical Arsenal

```text
Languages   : Go • Rust • Python • TypeScript • C • Shell
Infra/Cloud : GCP • Docker • Kubernetes • Linux • Nginx • GitHub Actions
Data/Store  : PostgreSQL • Redis • ClickHouse • SQLite • Vector DBs
Tooling     : Antigravity • Neovim • Git • Tmux • Linux CLI
```

---

### 📊 Telemetry

<div align="center">
  <img height="165em" src="https://github-readme-stats.vercel.app/api?username=0xrizz&show_icons=true&hide_border=true&bg_color=0d1117&title_color=f0f6fc&icon_color=c9d1d9&text_color=8b949e" />
  <img height="165em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=0xrizz&layout=compact&hide_border=true&bg_color=0d1117&title_color=f0f6fc&text_color=8b949e" />
</div>

---

### ⚡ Recent Activity

<!--START_SECTION:activity-->
* 🔄 Synchronizing activity log...
<!--END_SECTION:activity-->

---

### 📬 Collaboration & Inquiries

```text
┌──────────────────────────────────────────────────────────────────────────┐
│  💬 OPEN FOR COLLABORATION, ARCHITECTURE REVIEW & TECH TALKS             │
│                                                                          │
│  Building high-performance distributed backends, cloud systems, or       │
│  autonomous AI agent workflows? Let's connect.                           │
│                                                                          │
│  ❯ Email    : abdulmajidalkarim343@gmail.com                             │
│  ❯ LinkedIn : https://linkedin.com/in/0xrizz                             │
│  ❯ GitHub   : https://github.com/0xrizz                                  │
└──────────────────────────────────────────────────────────────────────────┘
```

<div align="center">

[ [✉️ Send Email](mailto:abdulmajidalkarim343@gmail.com) ] • [ [💼 LinkedIn](https://linkedin.com/in/0xrizz) ] • [ [🚀 Repositories](https://github.com/0xrizz?tab=repositories) ]

</div>
```

- [ ] **Step 2: Verify `README.md` markdown syntax and rendering integrity**
- [ ] **Step 3: Commit `README.md`**

```bash
git add README.md
git commit -m "feat: implement minimalist monospace profile readme"
```

---

### Task 2: Setup Dynamic Activity GitHub Actions Workflow

**Files:**
- Create: `.github/workflows/update-activity.yml`

**Interfaces:**
- Consumes: `README.md` with `<!--START_SECTION:activity-->` tags.
- Produces: Automated scheduled commit updating the activity log.

- [ ] **Step 1: Create `.github/workflows/update-activity.yml`**

```yaml
name: Update GitHub Activity

on:
  schedule:
    - cron: "0 */4 * * *" # Runs every 4 hours
  workflow_dispatch: # Allows manual trigger

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: write

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Update Recent Activity
        uses: jamesgeorge007/github-activity-readme@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          COMMIT_MSG: "chore: update recent activity [skip ci]"
          MAX_LINES: 5
```

- [ ] **Step 2: Verify workflow YAML syntax**
- [ ] **Step 3: Commit workflow file**

```bash
git add .github/workflows/update-activity.yml
git commit -m "ci: add automated recent activity updater workflow"
```
