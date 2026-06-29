# Publishing this as a public GitHub repo

Pick one path. Both leave you with an open (public) repo.

## Fastest — GitHub CLI (`gh`)
```bash
cd agentic-design-patterns-skills
git init
git add .
git commit -m "Agentic design pattern skills (selector + 21 patterns)"
gh repo create agentic-design-patterns-skills --public --source=. --remote=origin --push
```
(Install `gh` first if needed: https://cli.github.com — then `gh auth login`.)

## Manual — create on github.com, then push
1. Create a new **public** repo on github.com named `agentic-design-patterns-skills` (do **not** initialize it with a README/license — this folder already has them).
2. Then:
```bash
cd agentic-design-patterns-skills
git init
git add .
git commit -m "Agentic design pattern skills (selector + 21 patterns)"
git branch -M main
git remote add origin https://github.com/<your-username>/agentic-design-patterns-skills.git
git push -u origin main
```

## Before you push
- Edit `LICENSE` — replace `<YOUR NAME>` with your name.
- In `README.md`, replace `<your-username>` in the clone URL.
