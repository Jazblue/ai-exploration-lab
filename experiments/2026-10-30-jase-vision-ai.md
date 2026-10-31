# Jase Vision AI — image understanding prototype

**Date recorded:** 30 October 2026  
**Project site:** https://vision.jasoncv.click/  
**Role in the lab:** Computer-vision / multimodal experiment

## What is it meant to do?

Jase Vision AI is intended to become a business-oriented image analyser. The broad idea is similar to a document analyser, but the input is a photograph or image rather than a document.

A useful business workflow could eventually:
- describe the contents of an image in clear language;
- identify visible objects, products, equipment or scene details;
- extract readable text where the model supports it;
- produce a structured summary for a business user;
- flag uncertainty and ask for human review rather than invent details.

These are development goals, not claims that every feature is already implemented.

## Current model

- **Model:** MiniCPM-V 4.7 1B
- **Quantisation:** Q4_K_M
- **Runtime:** Ollama
- **Application stack:** Python with Flask, plus a web interface.

This is a compact vision-language model used for image understanding. It is not a custom model trained by this project. The application sends images to the locally hosted model and presents its responses.

## What has been tested

The prototype has been used to submit images and obtain natural-language descriptions of visible content, including people, clothing, objects and indoor surroundings.

This establishes a basic image-question-answering / description workflow. It does not yet establish reliable specialist inspection, perfect object recognition, OCR accuracy, or production-grade business reporting.

## Why this model?

The 1B model is small enough to experiment with on the available local setup. Its size makes it practical for prototyping, although capability and accuracy may be limited compared with larger vision models.

## Next experiments

1. Build a fixed set of representative business images.
2. Define a simple rubric: objects correctly identified, important details missed, invented details, and useful output.
3. Compare the current model with another vision-capable model using identical images and prompts.
4. Add structured output only after checking that the underlying observations are correct.
5. Record latency, memory use and failure cases.

## Limitations and honest status

The current system is an image-analysis prototype. The intended business use case is still being shaped. A model-generated description is an interpretation of an image, not a verified inspection or professional assessment.
