---
title: "How I Ran a Local LLM on My Android Phone, And What I Learned About Google’s AI Edge Gallery"
date: "2025-06-02"
tags:
    - llm
    - local-llm
    - google
    - edge-gallery
    - huggingface
    - large-language-models
thumbnail: "/assets/img/images-for-pages/artificial-intelligence/how-i-ran-a-local-llm.png"
---
## The Experiment: LLMs Running Locally on My Samsung Galaxy S23 FE
In an age where every AI app wants your data and an always-on cloud connection, I decided to flip the narrative:

What if I could run a large language model (LLM) entirely on my smartphone, offline, privately, and efficiently?

That’s when I stumbled upon Google AI Edge Gallery, an open-source, experimental Android app announced at Google I/O 2025. It promises offline generative AI on Android, no internet, no cloud, just your phone and the model.

Naturally, I had to test it.

---

## What Is Google AI Edge Gallery?
It’s not just an app, it’s a framework for running open-source LLMs and vision models entirely on-device. Some core features:
- Offline-first: Once you download a model (like from Hugging Face), you don’t need an internet connection.
- Modular UI: With modes like AI Chat, Prompt Lab, and Ask Image, it’s clearly built for tinkering.
- Model Flexibility: Supports quantized models like gemma-3–1b-it-q4, qwen2.5–1.5b-instruct-q8, and more.
All powered by Google’s LiteRT and AI Edge APIs, tailored for Android 10+ devices with ≥6GB RAM.

---

## Hardware: My Test Setup
- Device: Samsung Galaxy S23 FE
- Processor: Snapdragon 778G
- RAM: 8GB
- Model Tested: gemma3–1b-it-q4 from Hugging Face

---

## Benchmark Results on Google AI Edge Gallery
Model: gemma3–1b-it-q4
Device: Samsung Galaxy S23 FE
Prompt: “Explain black holes at a high-school level”

- First Token: 0.87 sec (time taken for the model to generate the very first token after receiving the prompt)
- Prefill Speed: 16.13 tokens/sec (speed at which the model processes the input prompt and prepares internal states)
- Decode Speed: 12.76 tokens/sec (rate at which the model generates output tokens)
- Total Latency: 61.37 sec (end-to-end time from prompt submission to final token generation)
For a 1B parameter model running entirely on a CPU-bound smartphone, this is impressive. The total response time, just over a minute, delivered a clear, coherent explanation with zero cloud dependency. On newer devices with Snapdragon 8 Gen 2+ and NPU offloading, you’d likely see faster decoding and lower latency.

## Other Models Available
The Gallery also lists:
- gemma-3n-e2b-it-int4–2B params, better quality, slower.
- gemma-3n-e4b-it-int4–4B params, risky on mobile, may crash.
- qwen2.5–1.5b-instruct-q8–1.5B params, better instruction-following, but slower due to 8-bit quantization.

---

## Trade-offs I Observed
- Speed: 1B models are usable (~12–16 tokens/sec); 2B+ models slow things down fast.
- Quality: Qwen and Gemma 2B+ provide richer answers, but your patience will be tested.
- RAM Use: 1B fits easily; 4B models flirt with crashes unless you have heavy-duty specs.
- Privacy: Full offline inference. Nothing leaves your device. Refreshing.
- User Control: You choose the model, quant level, and can even bring your own.

---

## Final Take
Google AI Edge Gallery is a bold move toward decentralized, local-first AI. It’s not trying to be ChatGPT, it’s a lab for developers, researchers, and tinkerers to explore edge inference. If you’re even slightly into privacy-preserving AI, LLM optimization, or Android-native ML, it’s worth a spin.

It’s also a wake-up call:
We no longer need the cloud to talk to large language models. Our phones are becoming inference engines.

---

*Interested in edge AI, LLMs, and practical analytics? Follow me here or at parashar.ca.*
