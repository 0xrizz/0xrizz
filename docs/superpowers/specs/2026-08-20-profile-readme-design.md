# Design Specification: 0xrizz Minimalist Monospace GitHub Profile

- **Target Repository**: `0xrizz/0xrizz` (`README.md`)
- **Aesthetic Direction**: Pure Monospace Terminal / Dark Minimalist (Zero generic colorful icons, high-density signal, custom ASCII art).
- **Date**: 2026-08-20
- **Status**: Ready for Implementation Plan

---

## 1. Overview & Objectives

Create an iconic, high-signal GitHub Profile README for **0xrizz** that establishes a sharp developer identity. The design eliminates standard colorful badges in favor of a clean, dark-mode terminal layout featuring:
1. Custom ASCII branding banner (`0xrizz`).
2. Structured monospace spec sheet / arsenal.
3. Dark minimalist GitHub telemetry (commits, stars, top languages) with a cohesive dark palette matching GitHub's dark theme.
4. Automated dynamic Recent Activity feed powered by GitHub Actions.
5. High-contrast, clean Call-To-Action (CTA) box for collaborations and tech discussions.

---

## 2. Visual Hierarchy & Components

```
┌─────────────────────────────────────────────────────────────┐
│  [HERO]: ASCII Art Logo (0xrizz) + Monospace Status Bar    │
├─────────────────────────────────────────────────────────────┤
│  [SPEC SHEET]: Profile Metadata in Clean YAML / Codeblock   │
├─────────────────────────────────────────────────────────────┤
│  [ARSENAL]: Pure Monospace Categorized Tech Stack           │
├─────────────────────────────────────────────────────────────┤
│  [TELEMETRY]: Custom Monochrome / Dark GitHub Stats Cards   │
├─────────────────────────────────────────────────────────────┤
│  [ACTIVITY]: Automated Recent Activity Feed (GitHub Action) │
├─────────────────────────────────────────────────────────────┤
│  [CTA BOX]: Monospace Collaboration & Inquiry Terminal Box  │
└─────────────────────────────────────────────────────────────┘
```

### Component Details

### A. Hero Section (ASCII Art & Status)
* **ASCII Art**: Clean, bold, monospace ASCII block lettering for `0xrizz`.
* **System Status Line**: Monospace status string:
  ```text
  [ status: online ] • [ role: systems_and_ai_engineer ] • [ env: linux/x86_64 ]
  ```

### B. Developer Spec Sheet (YAML Block)
* Concise representation of technical focus and philosophy without boilerplate text:
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

### C. Technical Arsenal (Pure Monospace / Zero Generic Icons)
* Categorized cleanly using monospace formatting:
  ```text
  Languages   : Go • Rust • Python • TypeScript • C • Shell
  Infra/Cloud : GCP • Docker • Kubernetes • Linux • Nginx • GitHub Actions
  Data/Store  : PostgreSQL • Redis • ClickHouse • SQLite • Vector DBs
  Tooling     : Antigravity • Neovim • Git • Tmux • Linux CLI
  ```

### D. Dark Minimalist Telemetry
* Integrated SVG cards with strict monochrome/dark palette matching GitHub's `#0d1117` dark background:
  - Card 1: **GitHub Stats** (Stars, Commits, PRs, Contributed Repos).
  - Card 2: **Top Languages** (Compact layout, custom unified monochrome accent).
* Parameters: `bg_color=0d1117`, `title_color=f0f6fc`, `text_color=8b949e`, `icon_color=c9d1d9`, `hide_border=true`.

### E. Dynamic Recent Activity (GitHub Actions)
* Target container in `README.md`:
  ```markdown
  ### ⚡ Recent Activity
  <!--START_SECTION:activity-->
  <!-- Dynamic content automatically updated by GitHub Action -->
  <!--END_SECTION:activity-->
  ```
* Automated via workflow `.github/workflows/update-activity.yml`.

### F. Terminal CTA Box (Call-To-Action)
* ASCII border box with direct contact channels:
  ```text
  ┌──────────────────────────────────────────────────────────────────────────┐
  │  💬 OPEN FOR COLLABORATION, CONSULTING & TECH INQUIRIES                  │
  │                                                                          │
  │  Looking to build robust distributed architectures, autonomous systems,  │
  │  or discuss engineering challenges? Let's connect.                       │
  │                                                                          │
  │  ❯ Email    : abdulmajidalkarim343@gmail.com                             │
  │  ❯ LinkedIn : linkedin.com/in/0xrizz                                     │
  │  ❯ GitHub   : github.com/0xrizz                                          │
  └──────────────────────────────────────────────────────────────────────────┘
  ```

---

## 3. Automation Architecture (GitHub Actions)

* **File**: `.github/workflows/update-activity.yml`
* **Schedule**: Runs every 4 hours (`cron: '0 */4 * * *'`) and on manual dispatch (`workflow_dispatch`).
* **Engine**: `jamesgeorge007/github-activity-readme@master`
* **Permissions**: `contents: write` (to commit the updated `README.md`).

---

## 4. File Manifest

1. `README.md` — The complete profile markdown.
2. `.github/workflows/update-activity.yml` — The GitHub Action automation workflow.
