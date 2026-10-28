# Agent Room ship target

Starter repo for Agent Room's optional **Ship** button. The room commits the newest website to
`site/index.html`; GitHub Actions then runs `tests/check.mjs` and, only if every check passes,
deploys `site/` to GitHub Pages.

## Set up (once)

1. Create an empty **public** GitHub repo (e.g. `agent-room-site`) and push the contents of this folder to `main`.
2. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Create a **fine-grained personal access token** (GitHub → Settings → Developer settings):
   - Repository access: **only** this repo
   - Permissions: **Contents: Read and write**, **Actions: Read-only**, **Pages: Read-only**
   - A short expiry (e.g. 30 days)
4. Add to Agent Room's `.env` (paste directly into the file, never into a chat):
   ```
   GITHUB_TOKEN=github_pat_...
   GITHUB_REPO=your-name/agent-room-site
   ```
5. Restart Agent Room. The **Ship** button in the preview panel turns on.

The token stays on the room's server. The agents never see it and can't trigger a deploy:
only a person pressing **Ship** does.
