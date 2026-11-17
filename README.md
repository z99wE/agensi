# Agensi — Video Production Agency

A fleet of Hermes Agent bots that debate, direct, edit, curate, and publish social video for X, LinkedIn, Instagram, and YouTube.

## Bots

| Bot | Role | Stack |
|-----|------|-------|
| `independent-filmmaker` | Independent filmmaker | OpenMotion reference-video recreation, Motion.md, brand kits |
| `lazy-filmmaker` | Lazy one-click filmmaker | MoneyPrinterTurbo topic/keyword → HD short video |
| `creative-strategist` | Agency lead / debate chair | Remocn, Ultrademo, AiEmcee |
| `scripter` | Scripts + narration.json + storyboard.json | AiEmcee, aidemo, Ultrademo |
| `director-1` | Animation director | Remotion + Remocn |
| `director-2` | Deterministic demo director | aidemo + definitely-not-a-robot |
| `director-3` | Human-capture director | definitely-not-a-robot + OpenTape |
| `director-4` | Narrated film director | AiEmcee + Remotion |
| `director-5` | Release trailer director | OpenTape + Rollcut + Ultrademo |
| `video-editor` | Assembly + captions + thumbnails | OpenTape, Rollcut, Ultrademo, ffmpeg |
| `curator-feedback-looper` | Quality gate / review loops | Ultrademo review, AiEmcee studio, Rollcut drift |
| `uploader-platforms` | X / LinkedIn / Instagram / YouTube publishing | Ultrademo, OpenTape, Rollcut |

## How it works

Each bot is a Hermes profile with its own `SOUL.md` persona. They debate in a Hermes group chat (Bots tab → Manage groups → New Group Chat). The Creative Strategist chairs: it restates the brief, proposes up to 3 directions, the group debates, then signs off before any director writes code.

Workflow:
1. User drops a brief in the group chat, tags `@creative-strategist`
2. Strategist proposes 3 directions; group debates and picks one
3. `@scripter` writes `narration.json` / `storyboard.json`
4. A director renders (Remotion, aidemo, AiEmcee, OpenTape, Rollcut, Ultrademo)
5. `@video-editor` assembles final cuts per platform
6. `@curator-feedback-looper` runs the review loop and approves
7. `@uploader-platforms` publishes to X, LinkedIn, Instagram, YouTube

## Model config

All bots are LLM-agnostic — no model, provider, or base URL is hardcoded. Each bot inherits whatever Hermes has configured at runtime. Set the model once in Hermes (`hermes model <name>`) and every bot uses it.

```
# model.default: <commented out>   # inherit from active Hermes config
# model.provider: <commented out>   # inherit from active Hermes config
# model.base_url: <commented out>   # inherit from active Hermes config
```

## Repo layout

```
bots/<bot-name>/SOUL.md   # each bot's persona + toolkit + collaboration rules
config/agency-config.md   # model/provider config per bot
```

External tool repos commanded by the bots:
- https://github.com/Remocn/remocn.git
- https://github.com/ultrademo-hq/ultrademo.git
- https://github.com/mrigankad/AiEmcee.git
- https://github.com/tandryukha/aidemo.git
- https://github.com/dougwithseismic/npm-definitely-not-a-robot.git
- https://github.com/remotion-dev/remotion.git
- https://github.com/aidankmcalister/OpenTape.git
- https://github.com/ArshadNyx/Rollcut.git
