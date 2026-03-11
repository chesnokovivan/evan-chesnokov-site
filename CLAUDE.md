# Personal Website — Evan Chesnokov

Static personal site for sharing with AI lab hiring managers (Anthropic, OpenAI, xAI).

## Stack

- Plain HTML + CSS, no frameworks
- Deployed via GitHub Pages (actions workflow in `.github/workflows/pages.yml`)
- Live at: https://chesnokovivan.github.io/evan-chesnokov-site/

## Design System

- Background: `#F5F2E8` (warm sand), Text: `#1A1A1A`, Accent: `#D97757` (terracotta)
- Fonts: Libre Baskerville (serif headlines), Inter (body), JetBrains Mono (code/labels)
- No emojis, no border-radius on content blocks, text-based section labels
- Reference: `~/.claude/skills/landing-page-design/SKILL.md`

## Structure

- `index.html` — main page (hero, work, projects, writing, footer)
- `writing/week-of-exponentials.html` — full essay page

## Content Rules

- No AI slop — all copy from actual CVs, essays, applications
- Hero leads with what he does (for sourcers), subtext drops BBC/NYT/physics (for curiosity)
- Work links use `../index.html` not `../` (fixes file:// directory listing bug)
- Company links open in new tabs, styled as `a.work-company`

## Dev Server

```
cd "/Users/evanchesnokov/Documents/Personal Projects/Active/evan-chesnokov-site"
python3 -m http.server 8787
```
