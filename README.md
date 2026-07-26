# kandev

Workflow definitions for [Kandev](https://kandev.dev), synced into my Kandev workspace via the
**GitHub Sync** settings feature.

## How it works

Kandev's GitHub Sync periodically polls a directory in this repo for workflow export files and
imports/updates the matching workflows in the workspace. Nothing needs to be run manually — just
commit and push, and Kandev picks up the change on its next poll.

## Structure

```
.kandev/workflows/
  workflows.yaml   # exported workflow definitions (kandev_workflow format)
```

Each file under `.kandev/workflows/` is a `.yml`/`.yaml`/`.json` export produced by the
**Export** action on a workflow in the Kandev app. Files are not meant to be hand-written —
edit the workflow in the app, re-export, and replace the file here.

## Adding or updating a workflow

1. In Kandev, open the workflow and run **Export**.
2. Save the exported file into `.kandev/workflows/`.
3. Commit and push to `main`.
4. Kandev syncs the change automatically (poll interval configured in
   Settings → GitHub Sync, minimum 60s).

## Sync configuration

In Kandev, Settings → GitHub Sync points at:

```
https://github.com/acusset/kandev/tree/main/.kandev/workflows
```
