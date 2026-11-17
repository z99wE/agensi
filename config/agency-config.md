# Agensi model/provider configuration

All bots run on Hermes's default model config — Fireworks `kimi-k2p6`. None are pinned to the local FCC launcher or any custom provider.

## Per-bot config

Each profile at `~/.hermes/profiles/<bot-name>/config.yaml` has:

```
model:
  default: "accounts/fireworks/models/kimi-k2p6"
  provider: "fireworks"
  base_url: "https://api.fireworks.ai/inference/v1"
```

## Bots covered

- creative-strategist
- scripter
- director-1
- director-2
- director-3
- director-4
- director-5
- video-editor
- curator-feedback-looper
- uploader-platforms
- critic
- scribe
- researcher

To change a bot's model: `hermes -p <bot-name> model <model>` or edit its `config.yaml` `model:` block directly.
