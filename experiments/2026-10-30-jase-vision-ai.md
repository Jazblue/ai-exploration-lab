# Jase Vision AI — image understanding prototype

**Date recorded:** 30 October 2026  
**Project site:** https://vision.jasoncv.click/  
**Role in the lab:** Computer vision / multimodal experiment

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

## Connecting the application to the web

The project is available at https://vision.jasoncv.click/. The application was connected to this domain through Cloudflare, making the experiment accessible through a dedicated web address rather than only through a local development interface.

This connection was a significant part of the build and a particularly enjoyable part of the experiment: bringing the model, Ollama runtime, Python/Flask application, web interface and domain access together made the result feel like a complete application.

An availability test also exposed an important deployment dependency: when the Python server was stopped, the website became unavailable. Cloudflare and the domain provide a route to the application; they do not by themselves keep the Flask process or model runtime running. The service therefore depends on the hosting environment, application server, model runtime and network/domain path being available.

The precise Cloudflare setup (such as the specific DNS, proxy or tunnel arrangement) is not asserted in this record because those implementation details have not been verified here. No IP addresses, credentials, tokens or private configuration belong in this public documentation.

## Why this model?

The 1B model is small enough to experiment with on the available local setup. Its size makes it practical for prototyping, although capability and accuracy may be limited compared with larger vision models.

## What the experiment taught me

The value of this project was not only the model's image descriptions. It was the process of integrating several technologies into one usable application: model inference through Ollama, Python/Flask application logic, a web interface, and Cloudflare-connected domain access.

This was one of the most enjoyable experiments of the week. The hands-on process of making the separate pieces work together was motivating and helped clarify an area worth developing further: practical, business-focused AI applications.

It also highlighted the difference between a working demo and a dependable hosted service. A successful test requires the model, runtime, application process and network path to be available, and each layer should be checked separately when troubleshooting.

## Next experiments

1. Build a fixed set of representative business images.
2. Define a simple rubric: objects correctly identified, important details missed, invented details, and usefulness of the output.
3. Compare the current model with another vision-capable model using identical images and prompts.
4. Add structured output only after checking that the underlying observations are correct.
5. Record latency, memory use and failure cases.
6. Document hosting and restart requirements so availability can be tested consistently.

## Limitations and honest status

The current system is an image-analysis prototype. The intended business use case is still being shaped. A model-generated description is an interpretation of an image, not a verified inspection or professional assessment.
