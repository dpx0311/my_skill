---
name: llmfit-advisor
description: Recommend local language models that fit the user's CPU, RAM, and GPU/VRAM. Use when comparing local model choices or estimating hardware fit; requires the llmfit CLI for live hardware data.
---

# llmfit advisor

Use the `llmfit` CLI only when installed and available. If it is unavailable, say so and offer a qualitative estimate from hardware details the user provides. Never invent hardware detection results.

## Workflow

1. Run `llmfit --json system` to get the detected hardware summary.
2. Run `llmfit recommend --json --limit 5` for general recommendations, or add `--use-case coding` for coding models.
3. Explain fit level, quantization, and estimated speed as estimates. Do not recommend models marked `TooTight`.
4. Do not download model weights, start serving processes, or change Ollama/LM Studio/vLLM configuration unless the user asks.

Install the CLI through the [upstream llmfit project](https://github.com/AlexsJones/llmfit). Skill source: `sources/llmfit/skills/llmfit-advisor/SKILL.md`.
