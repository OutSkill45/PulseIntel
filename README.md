# 🔍 PulseIntel

> **Real-time competitive marketing intelligence — powered by Firecrawl, Claude AI, and Supabase.**

[![Built with Bolt](https://img.shields.io/badge/Built%20with-Bolt-6C47FF?style=flat-square)](https://bolt.new)
[![Powered by Supabase](https://img.shields.io/badge/Backend-Supabase-3ECF8E?style=flat-square&logo=supabase)](https://supabase.com)
[![Scraped by Firecrawl](https://img.shields.io/badge/Scraping-Firecrawl-FF6B35?style=flat-square)](https://firecrawl.dev)
[![AI by Claude](https://img.shields.io/badge/AI-Claude%20API-CC785C?style=flat-square)](https://anthropic.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

---

## 📌 The Problem

Marketing and product teams waste hours every week manually checking competitor websites, pricing pages, and product changelogs. By the time they notice a competitor dropped prices or launched a feature, deals are already lost.

Existing tools like Crayon and Klue cost **$1,000+/month** and are built for enterprise. **PulseIntel is built for everyone else.**

---

## ✨ What PulseIntel Does

Add competitor URLs. We automatically scrape them using **Firecrawl**. Every time something meaningful changes — pricing, a new feature, a product announcement — **Claude AI** generates a sharp, human-readable intelligence brief:

- **WHAT CHANGED** — Factual summary in 1–2 sentences
- **WHY IT MATTERS** — Business implication for your team
- **RECOMMENDED ACTION** — One specific thing to do right now
- **IMPACT LEVEL** — LOW / MEDIUM / HIGH with reasoning

> *"Your competitor just dropped prices and launched a new feature. You found out in 30 seconds, not 3 weeks."*

---

## 🎯 Core Features (MVP)

| Feature | Priority |
|---|---|
| Add competitor URLs (homepage, pricing, changelog/blog) | ✅ Must Have |
| Firecrawl scraper → stores content in Supabase | ✅ Must Have |
| Diff detection — compare latest vs previous snapshot | ✅ Must Have |
| AI Summary via Claude (What Changed · Why · Action · Impact) | ✅ Must Have |
| Intelligence dashboard with competitor cards | ✅ Must Have |
| Manual "Scan Now" trigger button | ✅ Must Have |
| Change history / timeline view per competitor | 🔵 Should Have |
| Supabase Auth — basic login | 🔵 Should Have |
| Severity tags (Low / Medium / High) on AI summaries | 🔵 Should Have |
| Slack webhook alerts on high-impact changes | 🔵 Should Have |

---

## 🛠 How This Project Is Built

PulseIntel is built entirely using **browser-based platforms** — no software installation is needed by any team member.

| Platform | What It Does | Who Uses It |
|---|---|---|
| **[Bolt.new](https://bolt.new)** | AI-powered frontend builder — generates, hosts, and deploys the app entirely in the browser | Frontend team |
| **[Supabase](https://supabase.com)** | Cloud database, user authentication, and real-time data — managed via a web dashboard | Backend team |
| **[Firecrawl](https://firecrawl.dev)** | Scrapes competitor websites and returns clean, readable content | Backend team |
| **[Claude API](https://anthropic.com)** | Reads the scraped content and generates the intelligence summaries | Backend team |
| **[GitHub](https://github.com/OutSkill45/PulseIntel)** | Stores the project code, tracks every change, and coordinates the team | All team members |

> ⚡ **No downloads. No terminal. No installation required by anyone on the team.**

---

## 🗄 Database Structure (Supabase)

Three tables power the entire product. These are created directly inside the Supabase web dashboard — no coding required to set them up.

| Table | What it stores |
|---|---|
| `competitors` | Each competitor URL added by the user |
| `snapshots` | The scraped content from each competitor page, captured each time a scan runs |
| `intel_cards` | The AI-generated intelligence brief produced when a change is detected |

---

## 🚀 How the Project Is Set Up

> ⚠️ This project does **not** require cloning, installing packages, or running anything locally.
> All setup and building happens inside Bolt and Supabase's web dashboards.

### Step 1 — The app is built and hosted in Bolt

The entire frontend — the dashboard your users see and interact with — was built using [Bolt.new](https://bolt.new). Bolt uses AI to generate the code, and it hosts and deploys the app automatically in the cloud. Any changes to how the app looks or works are made directly inside the Bolt editor in your browser.

🔗 **Live Bolt project:** *(add your Bolt project link here)*
🌐 **Live deployed app:** *(add your Bolt deployment URL here)*

### Step 2 — The database is managed in Supabase

All competitor records, scraped snapshots, and AI intelligence cards are stored in a Supabase project. Supabase is a cloud database with a full web dashboard — no local database setup is needed. The Supabase project connects to the Bolt app automatically via the API keys configured in Step 3.

🔗 **Supabase project dashboard:** *(shared privately with the team — do not post publicly)*

### Step 3 — API keys live inside Bolt's environment settings

All sensitive API keys are stored securely inside the **Bolt project → Settings → Environment Variables** panel. Team members with Bolt editor access can view and update them there. They are never stored in GitHub.

| Key | Where to get it |
|---|---|
| `VITE_SUPABASE_URL` | Supabase → Project Settings → API |
| `VITE_SUPABASE_ANON_KEY` | Supabase → Project Settings → API |
| `FIRECRAWL_API_KEY` | [firecrawl.dev/dashboard](https://firecrawl.dev/dashboard) |
| `ANTHROPIC_API_KEY` | [console.anthropic.com](https://console.anthropic.com) |
| `SLACK_WEBHOOK_URL` | Slack App settings *(optional)* |

> 🔐 **Never paste API keys into GitHub files, issues, or comments.** They belong only in Bolt's environment settings panel.

### Step 4 — Bolt publishes the code to GitHub automatically

Bolt has a built-in **"Connect to GitHub"** feature. Once connected to the `OutSkill45/PulseIntel` repository, Bolt pushes the project code to GitHub every time a significant change is made. The team can then view, review, and comment on changes directly on the GitHub website — without touching any code locally.

**To connect Bolt to GitHub:**
1. Open your Bolt project
2. Click the **GitHub icon** in the top toolbar
3. Select **"OutSkill45"** as the organisation
4. Select **"PulseIntel"** as the repository
5. Choose the **`dev`** branch to push to
6. Click **"Connect"** — Bolt will sync automatically from that point on

---

## 📁 Project Structure

This is what you will see inside the GitHub repository. Bolt generates and manages these files — team members do not need to edit them directly.

```
PulseIntel/
├── src/
│   ├── components/       # All UI building blocks — cards, forms, buttons
│   ├── lib/
│   │   ├── supabase.ts   # Supabase database connection
│   │   ├── firecrawl.ts  # Competitor scraping logic
│   │   └── claude.ts     # AI intelligence summary pipeline
│   ├── pages/            # Each screen of the app
│   └── App.tsx           # The app's main starting point
├── docs/                 # Team guides and documentation
│   └── MARKDOWN_GUIDE.md # How to write and edit .md files
├── README.md             # This file — the project overview
└── CONTRIBUTING.md       # How every team member contributes
```

---

## 👥 Team Roles

| Role | Platform | What They Own |
|---|---|---|
| **Frontend** | Bolt editor | Dashboard UI, intelligence cards, competitor forms, Scan Now button, loading states |
| **Backend / Infra** | Supabase dashboard + Bolt env settings | Database tables, Firecrawl scraper, Claude API prompt pipeline, diff logic |
| **Docs & QA** | GitHub website | README, CONTRIBUTING, issue tracking, demo data, test notes |

---

## 🤝 Contributing

Every team member — coders and non-coders alike — contributes through the GitHub website or the Bolt editor. No installation is required. Please read [CONTRIBUTING.md](CONTRIBUTING.md) for the full step-by-step guide before making any changes.

---

## 📄 License

MIT © 2025 OutSkill45 / PulseIntel Team
