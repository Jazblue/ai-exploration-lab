# Experiment diary — 31 October 2026

## Focus: connecting the week's AI experiments

Today the work moved from building individual AI prototypes towards evaluating models more systematically.

### Jase Vision AI

The image analyser is intended as a business-oriented vision project, similar in concept to a document analyser but working with photographs. The current baseline is MiniCPM-V 4.7 1B in Q4_K_M quantisation, served locally through Ollama and connected to a Python/Flask application.

The immediate priority is not to add lots of features. It is to establish a repeatable image test set and find out which descriptions are correct, which details are missed, and when the model invents information.

### Local speech assistant

The speech experiment combined faster-whisper for transcription, Granite 4 3B through Ollama for responses, and Piper for spoken output. This was a useful systems-integration exercise: the complete assistant depends on several components working together, and each stage needs its own checks.

### Kaggle Qwen3 evaluation

The Huihui-Qwen3-8B-abliterated-v2 model loaded successfully on a Kaggle Tesla T4 using 4-bit quantisation. Initial tests showed mixed coding and security-analysis performance. The clearest failure was inventing website functionality and endpoints that were not in the inspected Maya Watson repository.

That failure is worth recording rather than hiding. It gives the lab a concrete reason to measure hallucinations and evidence quality.

## Lessons from the week

1. Different AI tasks need different models: vision, speech recognition, speech generation and text reasoning are not interchangeable.
2. A working prototype is not the same as a reliable product.
3. A model's confidence or detailed explanation does not establish that its claims are true.
4. Testing needs known inputs, expected outcomes and a record of failures.
5. Security testing must be based on verified application behaviour and remain within authorised scope.

## Next steps

- Create a small benchmark set for Jase Vision AI.
- Re-test the speech pipeline component by component.
- Continue Qwen evaluation using real source snippets and read-only evidence.
- Start a model register with versions, runtime, hardware and measured results.
