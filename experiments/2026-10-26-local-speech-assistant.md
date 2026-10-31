# Local speech assistant — Granite experiment

**Date recorded:** 26 October 2026  
**Project:** Granny / local speech assistant  
**Role in the lab:** Speech-to-text, language model and text-to-speech pipeline

## Objective

Experiment with a local voice assistant that can listen to spoken input, convert it to text, generate a response with a local language model, and speak the response aloud.

## Recorded stack

- **Speech recognition:** faster-whisper, `base` model, CPU / int8 configuration.
- **Language model:** Granite 4 3B served through Ollama.
- **Speech synthesis:** Piper, voice file `en_GB-alan-medium.onnx`.
- **Application:** Python-based local assistant.

The model's role is the conversational response. Whisper handles transcription and Piper handles speech generation; they are separate components, not one single speech model.

## What was learned

The experiment explored how separate local AI components can be connected into one voice workflow. It also exposed practical integration issues: microphone/audio handling, transcription quality, Python implementation errors and the need to test each stage independently.

## Evaluation still needed

- Measure transcription accuracy using repeatable sample recordings.
- Check response relevance and factual accuracy separately from speech quality.
- Measure end-to-end response time.
- Test noisy audio, different speaking speeds and failed microphone input.
- Record whether the assistant recovers cleanly from errors.

## Status

An experimental local prototype, not a finished voice product. The stack and settings above are the recorded setup; further testing is needed before making claims about reliability or performance.
