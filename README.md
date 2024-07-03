The local AI stack
==================
Goal: gather useful information on how to run AI locally (on-device).

[The Local AI Glossary](glossary.md)

Intro
-----

"Small" large language models (LLMs) have become more than good enough to efficiently run LLMs locally.
Models like Phi-3, Llama 3 and Gemma 2 are important enablers.
And together with hardware trends (e.g. NPUs and specialized hardware),
the future of AI will also be shaped outside the Cloud.
On-device AI applications running directly on the user's hardware have an edge regarding data privacy and building trust with users.

This repository explores the tech stack to enable local AI apps that run locally on device.
Besides the LLM, an individual semantic index (e.g. user specific) is the second key ingredient.
It's used to "make memories" and capture relevant user documents.
Under the hood, a vector database is used together with embedding models to enable RAG use cases.

Here, we also explore mobile phones and existing platforms to run this setup.

Local AI: Getting started
-------------------------
It's probably easier than you think: follow [these 3 simple steps in the ollama guide](ollama.md) to setup a local LLM.

Requirements to run Llama-3 8B:

* 5 GB free disk space
* A GPU with at least 6 GB VRAM
* Alternatively, a decent CPU will also result in good enough speeds,
  e.g. a recent 16-core CPU may already match your reading speed.
* For the CPU variant: ~ 6 GB of free RAM

Note: this applies to 4-bit quantization variant of the model (the default for Llama-3 when using ollama).
Running the FP16 model version roughly quadruples the disk and RAM/VRAM requirements.

Roadmap
-------
This project is still in its early stages. Check back in the future for updates:

* Information on different LLM Models
* Embedding models
* RAG
* LangChain
* ...
