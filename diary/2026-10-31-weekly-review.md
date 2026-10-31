# Experiment diary — 31 October 2026

## Focus: connecting the week's AI experiments

This week brought together several different areas of AI experimentation: building a practical vision application, integrating a speech assistant, and evaluating a larger language model. The work was not only about trying models; it was about connecting components into working systems and learning where they succeed or fail.

### Jase Vision AI

The image analyser is intended as a business-oriented vision project, similar in concept to a document analyser but working with photographs. The current baseline is MiniCPM-V 4.7 1B in Q4_K_M quantisation, served through Ollama and connected to a Python/Flask application.

The public-facing project is available at https://vision.jasoncv.click/. The application was connected to the domain through Cloudflare, bringing the model, Python application and web access together. This was an important part of the experiment: it was not simply running a model locally or in a terminal, but making an AI-powered application reachable through a proper project address.

A practical deployment lesson became clear when the Python server was stopped: the website became unavailable. The domain and Cloudflare connection provide the route to the application, but they do not keep the Python/Flask process running. The model runtime, application server, hosting environment and domain/network routing all have to be working for the complete service to be available. The exact Cloudflare configuration is not documented here because it has not been independently recorded.

Just as important as the technical result was the experience of building it. This was one of the week's most enjoyable experiments. Connecting the vision model to Ollama, wiring it into Flask, and then seeing the application available at its own domain made the project feel like a real, joined-up system. That enjoyment is useful feedback about the kind of work worth exploring further: practical AI projects where models, code, infrastructure and a usable interface come together.

### Local speech assistant

The speech experiment combined faster-whisper for transcription, Granite 4 3B through Ollama for responses, and Piper for spoken output. This was a useful systems-integration exercise: the complete assistant depends on several components working together, and each stage needs its own checks.

### Kaggle Qwen3 evaluation

The Huihui-Qwen3-8B-abliterated-v2 model loaded successfully on a Kaggle Tesla T4 using 4-bit quantisation. Initial tests showed mixed coding and security-analysis performance. The clearest failure was inventing website functionality and endpoints that were not present in the inspected Maya Watson repository.

That failure is worth recording rather than hiding. It gives the lab a concrete reason to measure hallucinations and evidence quality.

## Lessons from the week

1. Different AI tasks need different models: vision, speech recognition, speech generation and text reasoning are not interchangeable.
2. A working prototype is not the same as a reliable product.
3. A model's confidence or detailed explanation does not establish that its claims are true.
4. Testing needs known inputs, expected outcomes and a record of failures.
5. Security testing must be based on verified application behaviour and remain within authorised scope.
6. A public domain and routing layer do not replace a running application server; deployment is a chain of dependencies.
7. Enjoyment matters as a signal for future learning. The hands-on process of connecting the Jase Vision components was a highlight, not just a technical milestone.

## Next steps

- Create a small benchmark set for Jase Vision AI.
- Re-test the speech pipeline component by component.
- Continue Qwen evaluation using real source snippets and read-only evidence.
- Maintain a model register with versions, runtime, hardware and measured results.
- Document the Jase Vision hosting and availability requirements without publishing private infrastructure details.
