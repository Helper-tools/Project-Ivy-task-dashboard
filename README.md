# Project Ivy Task Dashboard

A local dashboard for **Project Ivy: Online Ranking** that shows every claimed Handshake task with its exact pipeline stage, build status, title, and latest update.

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
- Estimated pay for tasks that reached Ready to Deliver or Delivered after July 29, 2026
- Copyable filtered task lists

The pay card counts each qualifying task once at `$225`. It is an estimate based on the current Handshake stage and task update date; Handshake's Payments page remains the source of truth for posted earnings.

## Project configuration

Project Ivy is the default:

```text
https://ai.joinhandshake.com/fellow/aebaf7d0-8cc1-4b11-82bc-3a57a2f4ff4f/tasks
```

To use another project, copy `config.example.json` to `config.json` and change `projectName` and `projectTasksUrl`. `config.json` is ignored by Git.

## Test

```bash
npm test
```

## Attribution

This repository is an Ivy-focused fork of [Rhy-Shah/Project-H-task-dashboard](https://github.com/Rhy-Shah/Project-H-task-dashboard). The original project supplied the local dashboard, Playwright login flow, and Handshake API integration.
