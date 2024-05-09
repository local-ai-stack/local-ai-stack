Ollama
======
[Ollama](https://ollama.com/) is a simple way to start with running an LLM locally.

Setup is quite easy:
* Download ollama: https://ollama.com/download
* Execute `ollama pull llama3` to download a model, in this case Llama-3 (8B)
* Execute `ollama run llama3` to run the model

This is all it needs. Enter your prompt and the LLM will answer.

Notes:

* The `pull` step is optional; `run` will automatically download a model that does not exist yet. 
* ollama is "just" a wrapper around [llama.cpp](https://github.com/ggerganov/llama.cpp),
  which is also a nice way to run local LLMs.