# Ivy and Roadhouse Task Dashboard

This is a local dashboard for Handshake AI fellows working on Ivy and Roadhouse.

It shows your claimed tasks, the real stage each task is in, build status, task title, last update time, and an estimated pay total for tasks that reached Ready to Deliver or Delivered. It also includes a short FAQ for the questions people keep asking in Slack.

Your Handshake login stays on your computer. The saved login file is ignored by Git and is not pushed to GitHub.

## How to set it up

First, clone the repo and install everything:

```bash
git clone https://github.com/Helper-tools/Project-Ivy-task-dashboard.git
cd Project-Ivy-task-dashboard
npm install
npx playwright install chromium
```

Then start the dashboard:

```bash
npm start
```

Open this in your browser:

```text
http://localhost:4173
```

Click **Login**, sign in to Handshake, and wait for the dashboard to load your tasks. If the login window does not close by itself, go back to the dashboard and click **Save Login**.

## What you can do with it

- Switch between Ivy and Roadhouse.
- See which stage each task is currently in.
- Find tasks that are Ready to Deliver, Delivered, in review, or need fixing.
- Search and filter by task ID, stage, build status, title, or date.
- Copy the filtered task IDs.
- See an estimated pay total for eligible tasks.
- Read quick answers to common Ivy and Roadhouse questions.

## Payment estimate

The dashboard estimates pay at `$225` per eligible task.

For Ivy, it counts Ready to Deliver or Delivered tasks updated after July 29, 2026.

For Roadhouse, it counts every task currently in Ready to Deliver or Delivered.

This is only an estimate. The Handshake Payments page is still the source of truth.

## Change the projects

The repo already has Ivy and Roadhouse set up. To use different Handshake task pages, copy `config.example.json` to `config.json` and edit the `projects` list.

`config.json` is ignored by Git, so each person can keep their own setup.

## Run tests

```bash
npm test
```

## Credit

This is based on [Rhy-Shah/Project-H-task-dashboard](https://github.com/Rhy-Shah/Project-H-task-dashboard). This version adds Ivy and Roadhouse tabs, payment rules, and the FAQ.
