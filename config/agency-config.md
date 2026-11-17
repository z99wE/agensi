# Agensi model/provider configuration

## LLM-agnostic by design

No bot pins a specific model, provider, or base URL. Each bot inherits whatever LLM Hermes has configured at runtime — no cloud model is hardcoded, no provider is forced.

```
# model.default: <commented out>   # inherit from active Hermes config
# model.provider: <commented out>   # inherit from active Hermes config
# model.base_url: <commented out>   # inherit from active Hermes config
```

To change the LLM for all bots at once, set it in Hermes's active config:
```
hermes model <model-name>
```

Or per-bot:
```
hermes -p <bot-name> model <model-name>
```

## Bots covered

- independent-filmmaker
- lazy-filmmaker
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
