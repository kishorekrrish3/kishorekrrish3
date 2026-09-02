# Setting Up Automation on GitHub

This profile README uses three GitHub Actions workflows to keep all charts, calendars, stats, and project cards updated automatically.

---

## 1. Set Repository Workflow Permissions (Required)

Workflows need permission to commit updated SVGs back to your repository and push to the `output` branch:

1. In this repo, go to **Settings** → **Actions** → **General**.
2. Scroll to **Workflow permissions**.
3. Select **Read and write permissions**.
4. Click **Save**.

---

## 2. Generate a Personal Access Token (`METRICS_TOKEN`)

The metrics workflow (`metrics.yml`) needs a GitHub Personal Access Token (Classic) to read your contribution history, streak, and achievements.

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens) → **Generate new token (classic)**.
   > **Note**: Use **Classic**, not Fine-grained tokens.
2. Set note: `METRICS_TOKEN`.
3. Scopes:
   - Check `read:user`
   - Check `repo` (optional: tick this if you want private repository contributions counted in totals).
4. Click **Generate token** and copy the token value.
5. In your profile repo, go to **Settings** → **Secrets and variables** → **Actions** → **New repository secret**.
6. Name: `METRICS_TOKEN`
7. Value: Paste your token and click **Add secret**.

---

## 3. Trigger Workflows Manually for First-Time Setup

1. In this repo, navigate to the **Actions** tab.
2. If GitHub shows an "enable workflows" banner, click it.
3. In the left sidebar, click each workflow and run it manually via **Run workflow**:
   - **Metrics** (draws 3D isometric calendar, languages breakdown, achievements)
   - **Snake** (generates dark/light snake animations and pushes to the `output` branch)
   - **Charts and cards** (updates radars, stats, and project cards)

---

## 4. Local Preview

To preview all generated assets across dark and light modes before pushing:
- Open `preview.html` in your browser.
