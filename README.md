# Ivy and Roadhouse Task Dashboard

A local dashboard for **Project Ivy: Online Ranking** and **Project Roadhouse** that shows every claimed Handshake task with its exact pipeline stage, build status, title, and latest update. Project tabs keep each task list and activity history separate.

The dashboard uses your signed-in Handshake session. Login information is stored only in a local, ignored `auth.json` file and is never committed to GitHub.

## Run it

```bash
git clone https://github.com/Helper-tools/Project-Ivy-task-dashboard.git
cd Project-Ivy-task-dashboard
npm install
npx playwright install chromium
npm start
```

Open [http://localhost:4173](http://localhost:4173), select **Login**, and sign in to Handshake in the window that opens. If the window does not close automatically after login, return to the dashboard and select **Save Login**.

## What it shows

- Exact pipeline stage, including review and delivery stages
- Build status
- Task title and ID
- Last update time
- Search, stage, build, and date filters
- Quick groups for accepted tasks, tasks in review, and tasks needing action
- Separate Ivy and Roadhouse tabs
- Project-specific estimated pay for Ready to Deliver and Delivered tasks
- Hover help for the payment estimate
- The team's Slack FAQ plus the repeated Ivy/Roadhouse tasking answers for task batches, stage checks, task files, payment timing, rejected-task feedback, referrals, project access, reviewer selection, and Yukon work authorization
- Copyable filtered task lists

The pay card counts each qualifying task once at `$225`. Ivy only counts qualifying tasks updated after July 29, 2026. Roadhouse counts every task currently in Ready to Deliver or Delivered. Handshake's Payments page remains the source of truth for posted earnings.

## Project configuration

The dashboard includes both projects by default:

```text
https://ai.joinhandshake.com/fellow/aebaf7d0-8cc1-4b11-82bc-3a57a2f4ff4f/tasks
https://ai.joinhandshake.com/fellow/5df1908e-d347-46ae-b522-2bd363b7477a/tasks
```

To change the projects, copy `config.example.json` to `config.json` and edit the `projects` list. Use `paymentCutoff: null` when every current RTD or Delivered task should count. `config.json` is ignored by Git.

## Test

```bash
npm test
```

## Attribution

This repository is an Ivy-focused fork of [Rhy-Shah/Project-H-task-dashboard](https://github.com/Rhy-Shah/Project-H-task-dashboard). The original project supplied the local dashboard, Playwright login flow, and Handshake API integration.
