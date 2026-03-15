# Personal Website — Evan Chesnokov

Static personal site for AI lab hiring managers (Anthropic, OpenAI, xAI).

## Stack

- Plain HTML + CSS, no frameworks (main site)
- WebGL terminal mode: Three.js + xterm.js + cool-retro-term-renderer (built with tsup)
- Deployed via GitHub Pages → https://chesnokovivan.github.io/evan-chesnokov-site/

## Design System

- Background: `#F5F2E8` (warm sand), Text: `#1A1A1A`, Accent: `#D97757` (terracotta)
- Fonts: Libre Baskerville (serif headlines), Inter (body), JetBrains Mono (code/labels)
- No emojis, no border-radius on content blocks, text-based section labels

## Structure

- `index.html` — main page (hero, work, projects, writing, footer + terminal toggle)
- `writing/week-of-exponentials.html` — full essay page
- `terminal/` — WebGL CRT terminal mode
  - `index.html` — entry point, loads `dist/index.global.js`
  - `dist/index.global.js` — built bundle (Three.js + xterm.js + CRT shaders)
  - `assets/content/bios.txt` — boot sequence text (@@@ = 500ms pause)
- `me_pixel_still.png` / `me_pixel_anim.apng` — pixel avatar (favicon + hero)

## Terminal Mode

- **Entry**: click `>_` button or type "crt" on main page → CRT-off animation → navigate to `terminal/`
- **Exit**: type `exit` command or click `× exit` button → back to `index.html`
- **Color**: amber phosphor `#FFB000` (patched via sed from green `#0ccc68` in built JS)
- **Source**: forked from github.com/remojansen/remojansen.github.io, customized in `/tmp/evan-crt-ref/`
- **Rebuild**: `cd /tmp/evan-crt-ref && npx tsup --minify`, then copy + sed patch amber
- **Content**: ShellEmulator.ts has virtual filesystem (about.txt, Documents/work.txt, Projects/, Writing/)
- **Commands**: help, whoami, ls, cd, cat, clear, exit

## Content Rules

- No AI slop — all copy from actual CVs, essays, applications
- Hero leads with what he does, subtext drops BBC/NYT/physics
- Work links use `../index.html` not `../` (fixes file:// directory listing bug)

## Dev Server

```
python3 -m http.server 8787
```
