# Copilot Handoff — PixelPop-firmware (public OTA + feed repo)

**What:** Public distribution repo read by PixelPop boards: OTA binary `PixelPop.ino.bin`, and the Chicago Events feed `chicagoEvents.json` + `chicagoEvents-images/`. Source code lives in rauls4/PixelPop.
**Location:** `~/dev/PixelPop Project/PixelPop-firmware` · **GitHub:** rauls4/PixelPop-firmware (public)
**Branch:** `main`. HEAD moves several times a day (the Nextdoor exporter on Mini.local commits the feed at 07:00 and 15:00 CT), so always `git pull` first.

## Rules specific to this repo
- Do **not** publish OTA (`PixelPop.ino.bin`) unless Raul asks. Never publish 1.1.170–1.1.174 or 1.1.191–1.1.193 without Raul. Public OTA is 1.1.190 as of 2026-10-07.
- The feed is written by the exporter (`tools/nextdoor-container` in rauls4/PixelPop, deployed in `/Users/raul/nextdoor-container` on Mini.local). Don't hand-edit it.
- Boards fetch via raw.githubusercontent.com with a jsDelivr fallback.

## Build / run
No build. Nothing to test here.

## Standing rules for AI agents
- Keep this doc current after every meaningful change: branch, HEAD sha, state, next steps. Then commit and push.
- Never commit secrets: `.env`, `.dev.vars`, keystores (`*.jks`, `*.keystore`, `keystore.properties`), `local.properties`, signing certs (`*.p12`), API keys, login sessions.
- Never force-push, rewrite pushed history, or delete branches without Raul's explicit OK.
- Don't commit build output (`build/`, `Build/`, `DerivedData/`, `.gradle/`, `node_modules/`).
- Write "unknown" rather than guessing.
