# AI Exploration Lab

An independent research journal for experimenting with AI models, building practical prototypes, and recording what works, what fails, and what needs further testing.

This repository is deliberately evidence-led. It distinguishes confirmed results from plans, assumptions, and unfinished work.

## Current experiments

| Project | Model / stack | Purpose | Current status |
|---|---|---|---|
| [Jase Vision AI](experiments/2026-10-30-jase-vision-ai.md) | MiniCPM-V 4.7 1B (Q4_K_M) via Ollama; Python/Flask | Image understanding with a future business-analysis focus | Prototype |
| [Local speech assistant](experiments/2026-10-26-local-speech-assistant.md) | Granite 4 3B, faster-whisper, Piper | Local speech-to-text, language response and spoken output | Experimental prototype |
| [Qwen3 model evaluation](experiments/2026-10-31-qwen3-kaggle-evaluation.md) | Huihui-Qwen3-8B-abliterated-v2, 4-bit on Kaggle Tesla T4 | Evaluate coding, reasoning and defensive security analysis | In progress |

## Repository map

- `experiments/` — individual project and model test records.
- `diary/` — dated notes about progress, problems and lessons.
- `models/` — model register and intended roles.
- `results/` — future repeatable comparisons and scorecards.
- `safety/` — scope and rules for authorised defensive testing.

## How experiments are recorded

Each entry should include:
1. Date and objective.
2. Exact model name and runtime where known.
3. Prompt or test method.
4. Observed result, including failures.
5. What the result does and does not prove.
6. Next experiment.

Scores should only be added when the test has a defined rubric and can be repeated. A plausible answer is not proof of correctness.

## Principles

- Verify model output against real files, source code, and test results.
- Do not publish credentials, tokens, private configuration, personal data, or sensitive infrastructure details.
- Cybersecurity experiments must be authorised, controlled and non-destructive.
- Treat model-generated security findings as hypotheses until independently verified.
- Do not describe a prototype as a trained or production-ready model unless that is demonstrably true.

## Current focus

Explore practical AI development across vision, speech and language models while continuing to build reliable evaluation habits.
