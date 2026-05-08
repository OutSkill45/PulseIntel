# 🤝 Contributing to PulseIntel

Welcome to the PulseIntel team! This guide tells every team member — regardless of technical background — exactly how to contribute to this project. You do not need to install anything. Everything is done through websites in your browser.

---

## 📋 Table of Contents

- [How the Team Works](#how-the-team-works)
- [The Two Platforms You Will Use](#the-two-platforms-you-will-use)
- [Getting Access](#getting-access)
- [Team Roles & What Each Person Does](#team-roles--what-each-person-does)
- [How to Contribute — By Role](#how-to-contribute--by-role)
- [How Branching Works in Bolt](#how-branching-works-in-bolt)
- [How to Review Someone's Work on GitHub](#how-to-review-someones-work-on-github)
- [Naming Your Changes](#naming-your-changes)
- [The Golden Rules](#the-golden-rules)
- [What Never Goes on GitHub](#what-never-goes-on-github)
- [Need Help?](#need-help)

---

## 👥 How the Team Works

PulseIntel is built as a team across three roles. Each role has a clear home platform and clear ownership. There is no overlap — everyone knows what they own.

| Role | Home Platform | GitHub Handle |
|---|---|---|
| **Frontend** | Bolt editor | `@handle` |
| **Backend / Infra** | Supabase + Bolt env settings | `@handle` |
| **Docs & QA** | GitHub website | `@handle` |

> Replace `@handle` with your actual GitHub usernames before publishing.

---

## 🖥 The Two Platforms You Will Use

### Everyone uses GitHub (the website)
[github.com/OutSkill45/PulseIntel](https://github.com/OutSkill45/PulseIntel)

This is where all the project's files are stored and tracked. You use the GitHub website to:
- View the latest project files
- Upload documents and guides
- Track tasks on the project board
- Review and comment on changes
- Read the history of what has changed and why

**You use the GitHub website only — no downloads, no terminal.**

### Developers additionally use Bolt
[bolt.new](https://bolt.new)

Bolt is an AI-powered app builder that runs entirely in your browser. The developer(s) on the team build the app here. Bolt automatically pushes code changes to GitHub, so the rest of the team can always see the latest version without ever opening Bolt themselves.

---

## 🔑 Getting Access

### Step 1 — Accept the GitHub Organisation invite

1. Check the email address you used to sign up for GitHub
2. Look for an invite from **OutSkill45**
3. Click **"View invitation"** in the email
4. Click **"Join OutSkill45"**
5. You now have access to the PulseIntel repository

### Step 2 — Find the repository

1. Go to [github.com](https://github.com) and sign in
2. Click the dropdown at the top-left next to your photo
3. Select **OutSkill45**
4. Click **PulseIntel** — you are now inside the project

### Step 3 — Bookmark these links

Save these to your browser so you can always get back quickly:

- 📁 **GitHub repo:** `https://github.com/OutSkill45/PulseIntel`
- 📋 **Project board:** `https://github.com/orgs/OutSkill45/projects` *(add direct link once created)*
- ⚡ **Live app:** *(add Bolt deployment URL once available)*

---

## 🎭 Team Roles & What Each Person Does

### 🎨 Frontend — Works in Bolt

You are responsible for everything the user sees and clicks. You work inside the Bolt editor in your browser.

You own:
- The dashboard layout and design
- The competitor list and "Add Competitor" form
- Intelligence cards showing What Changed / Why / Action / Impact
- The "Scan Now" button
- Loading states, empty states, and error messages
- The overall look, feel, and colour scheme

You do **not** need to touch Supabase or the GitHub website for day-to-day work — Bolt handles syncing to GitHub automatically.

---

### 🔧 Backend / Infra — Works in Supabase + Bolt

You are responsible for everything behind the scenes. You work in the Supabase web dashboard and in Bolt's environment settings panel.

You own:
- Creating the three database tables in Supabase (`competitors`, `snapshots`, `intel_cards`)
- Connecting Firecrawl to the project (via API key in Bolt)
- Writing the scraping logic and the diff detection
- Connecting the Claude API and writing the prompt that generates intelligence summaries
- Making sure the Bolt frontend can read data from Supabase correctly

---

### 📝 Docs & QA — Works on GitHub website

You are responsible for the project's documentation and quality checking. You work entirely on the GitHub website.

You own:
- Keeping `README.md` and `CONTRIBUTING.md` up to date
- Writing and maintaining files in the `docs/` folder
- Creating and managing issues on the GitHub project board
- Checking the live app works before demos
- Pre-seeding the database with compelling demo data in Supabase
- Capturing screenshots for the demo presentation

---

## 🪜 How to Contribute — By Role

### If you are Docs & QA (GitHub website only)

This is the full workflow for uploading, creating, or editing any file on GitHub:

**To upload a document or image:**
1. Go to [github.com/OutSkill45/PulseIntel](https://github.com/OutSkill45/PulseIntel)
2. Make sure you are on the **`dev`** branch — check the dropdown near the top left that shows the branch name. If it says `main`, click it and select `dev`
3. Navigate into the folder you want to upload into (e.g. click `docs/`)
4. Click **"Add file"** → **"Upload files"**
5. Drag your file in, or click to browse
6. In the **"Commit changes"** section at the bottom, write a short description: e.g. *"Add demo script for presentation"*
7. Select **"Commit directly to the `dev` branch"**
8. Click **"Commit changes"**

**To create a new Markdown file:**
1. On the repo homepage, make sure you're on `dev`
2. Click **"Add file"** → **"Create new file"**
3. Type the path and filename at the top — e.g. `docs/demo-notes.md`
4. Write your content in the editor (see `docs/MARKDOWN_GUIDE.md` for formatting help)
5. Commit with a clear message and commit to `dev`

**To edit an existing file:**
1. Click the file to open it
2. Click the **pencil icon** (✏️) in the top right
3. Make your edits
4. Scroll down, write a commit message, commit to `dev`

---

### If you are Frontend (Bolt)

Your day-to-day workflow lives entirely inside Bolt. GitHub is updated automatically when Bolt pushes changes.

**To make a UI change:**
1. Open your Bolt project
2. Describe the change you want to the Bolt AI, or edit the component directly
3. Preview the result in Bolt's live preview panel
4. When happy, use Bolt's **GitHub sync** to push the change
5. In Bolt's GitHub panel, write a short description of what changed before pushing — e.g. *"Update intelligence card layout with severity badge"*

**To create a new feature branch in Bolt:**
See the [How Branching Works in Bolt](#how-branching-works-in-bolt) section below.

---

### If you are Backend / Infra (Supabase + Bolt)

**To create or update a database table:**
1. Go to your Supabase project dashboard
2. Click **"Table Editor"** in the left sidebar
3. Click **"New table"** or click an existing table to modify it
4. Add your columns with the correct data types
5. Enable **Row Level Security (RLS)** on the table
6. Document the change — add a note to `docs/database-schema.md` on GitHub describing what you added and why

**To update an API key or environment variable:**
1. Open the Bolt project
2. Click **Settings** → **Environment Variables**
3. Add or update the key
4. The app will reload automatically with the new value
5. Never paste the actual key value anywhere on GitHub

---

## 🌿 How Branching Works in Bolt

A **branch** is a safe copy of the project where you can make changes without affecting the main working version. Think of it like working on a duplicate of a Google Doc — you only merge it back once you're happy with it.

PulseIntel uses two permanent branches:

| Branch | What it is |
|---|---|
| `main` | The final, polished version — only updated when something is fully ready |
| `dev` | The working version — all day-to-day changes go here first |

**All contributions go to `dev` first. Never contribute directly to `main`.**

### Creating a branch in Bolt for a new feature:

1. In your Bolt project, look for the **branch selector** (usually in the top bar or settings)
2. Make sure you are currently on `dev`
3. Click **"Create new branch"**
4. Name it using the convention below — e.g. `feat/scan-now-button`
5. Build your feature on this branch
6. When complete, push to GitHub and open a Pull Request to merge into `dev`

### Branch naming — keep it simple and clear:

| Type of change | Format | Example |
|---|---|---|
| New feature | `feat/what-it-does` | `feat/intelligence-cards` |
| Fix something broken | `fix/what-was-broken` | `fix/empty-dashboard-state` |
| UI / visual change | `ui/what-changed` | `ui/severity-badge-colours` |
| Database change | `db/what-changed` | `db/add-intel-cards-table` |
| Documentation | `docs/what-changed` | `docs/update-team-roles` |

Rules: lowercase only, hyphens between words, no spaces.

---

## 🔃 How to Review Someone's Work on GitHub

When a team member finishes a change, they open a **Pull Request (PR)** — a formal request to merge their branch into `dev`. Everyone on the team can review and comment.

**To review a Pull Request:**
1. Go to the repo and click the **"Pull requests"** tab
2. Click the open PR you want to review
3. Read the description — what did they change and why?
4. Click **"Files changed"** to see exactly what was added or modified
5. To leave a comment on a specific line, click the **"+"** icon that appears when you hover over a line
6. When done, click **"Review changes"**
   - Choose **"Approve"** if it looks good
   - Choose **"Request changes"** if something needs fixing
7. Add a short comment and submit your review

**Once approved:** the author (or team lead) clicks **"Merge pull request"** to bring the changes into `dev`.

---

## ✍️ Naming Your Changes (Commit Messages)

Every time you save a change to GitHub you write a short commit message. This is the team's history — make it readable.

Use this simple format: `type: what you did`

| Prefix | Use when |
|---|---|
| `feat:` | Adding something new |
| `fix:` | Correcting something broken |
| `ui:` | Changing how something looks |
| `db:` | Changing the database |
| `docs:` | Updating documentation |
| `content:` | Adding demo data, copy, or assets |

**Good examples:**
```
feat: add Scan Now button to competitor dashboard
fix: intelligence cards not loading on refresh
ui: update severity badge to red/amber/green colours
docs: add demo script to docs folder
db: create snapshots table in Supabase
content: seed 5 competitor examples for demo
```

**Bad examples:**
```
update
changes
wip
stuff
aaa
```

---

## 🏅 The Golden Rules

Five rules that keep the team working smoothly:

1. **Always work on `dev`, never directly on `main`** — main is the clean, finished version. dev is the workshop.

2. **Write a clear message every time you commit** — "Added stuff" helps no one. "Add severity badge to intel card" is perfect.

3. **Check you're on the right branch before making changes** — look at the branch name in the top-left dropdown on GitHub before editing anything.

4. **Never put API keys on GitHub** — not in files, not in commit messages, not in issue comments. Ever. Keys live in Bolt's environment settings only.

5. **When unsure, ask in Slack first** — a 2-minute message prevents hours of untangling.

---

## 🚫 What Never Goes on GitHub

| What | Why |
|---|---|
| API keys of any kind | Security risk — if exposed, must be regenerated immediately |
| Passwords or login credentials | Same reason |
| Personal data of real users | Privacy issue |
| Large video files | GitHub is not a video host — use Google Drive or Loom |
| Supabase dashboard screenshots with keys visible | Crop or blur sensitive values before uploading |

If you accidentally commit something sensitive, **tell the team lead immediately** — don't try to fix it yourself.

---

## 💬 Need Help?

| Problem | Where to go |
|---|---|
| Can't find the PulseIntel repo | Check your email for the OutSkill45 invite and accept it |
| Not sure which branch you're on | Look at the branch dropdown top-left on GitHub — switch to `dev` if needed |
| Bolt is showing an error | Post a screenshot in the team Slack channel |
| Supabase table not working | Check the Supabase logs in the dashboard → Logs section |
| Made a mistake on GitHub | Tell the team lead — don't try to fix it alone |
| Don't know how to format a Markdown file | Read `docs/MARKDOWN_GUIDE.md` in this repo |
| Claude API not generating summaries | Check the API key in Bolt env settings, then check [status.anthropic.com](https://status.anthropic.com) |
| Firecrawl returning empty results | Verify the competitor URL is correct and publicly accessible |

---

*PulseIntel · Built by OutSkill45 · No installation required · GitHub website + Bolt + Supabase*
