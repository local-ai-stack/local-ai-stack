The local AI stack
==================
Goal: gather useful information on how to run AI locally (on-device).

[The Local AI Glossary](glossary.md)

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
