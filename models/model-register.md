# Model register

This register records the models used in the lab and the job each one performs. Versions and settings should be updated when they change.

| Model / component | Role | Runtime / setup | Project |
|---|---|---|---|
| MiniCPM-V 4.7 1B, Q4_K_M | Image understanding / vision-language | Ollama, local Python/Flask app | Jase Vision AI |
| Granite 4 3B | Conversational language response | Ollama | Local speech assistant |
| faster-whisper `base` | Speech-to-text | CPU / int8 | Local speech assistant |
| Piper `en_GB-alan-medium.onnx` | Text-to-speech | Local Piper runtime | Local speech assistant |
| Huihui-Qwen3-8B-abliterated-v2 | General text, coding and reasoning evaluation | Kaggle Tesla T4, Transformers, BitsAndBytes 4-bit | Model evaluation |

## Important distinction

Whisper and Piper are speech pipeline components, not alternative chat language models. MiniCPM-V is the current Jase Vision baseline; it is not a model trained specifically for a business domain. The Qwen model is being evaluated, not adopted as a trusted security tool.
