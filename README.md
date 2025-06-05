# 🔁 GitHub Auto Commit Bot

This repository uses **GitHub Actions** to automatically commit a timestamped file (`report.txt`) to the repository on a custom schedule.

## 🧠 What It Does

- Creates a file `report.txt` (or appends to it) with the current timestamp (in seconds).
- Commits and pushes the file to the repo.
- Uses `cron` schedules to trigger commits **multiple times per day across all months**.
- Useful for:
  - Keeping GitHub contributions graph active
  - Testing Git automation
  - Triggering workflows regularly

## ⚙️ How It Works

The workflow is defined in `.github/workflows/auto-commit.yml`:

```yaml
- run: date +%s >> report.txt
- run: git config --global user.name 'Automated Bot'
- run: git commit -am "Automated report"
- run: git push
