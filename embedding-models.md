Embedding Models for the Local AI Stack
=======================================
Typically, you want a specialized embedding model to create the vector embeddings for documents.

Huggingface MTEB leaderboard
----------------------------
The [MTEB leaderboard](https://huggingface.co/spaces/mteb/leaderboard) gives a good first impression of available embedding models.
It comes with quality scores, model sizes, memory requirements and vector dimensions. 

Embedding models well suited for local AI
-----------------------------------------

### mxbai-embed-large

High quality text embeddings model that is relatively small.

* 670 MB (F16)
* 1024 dims
* Time to embedd 12 docs (CPU only, AMD Ryzen 9 5950X): 2.2s
* `ollama pull mxbai-embed-large`
* LangChain: `embeddings = OllamaEmbeddings(model="mxbai-embed-large")` 

### bge:small-en

Twice as fast as mxbai-embed-large and uses much lower resources.
Quality seems fine for e.g. testing; did not investigate real use cases yet.
Uses only 384 dimensions, which has advantages:
 * Embeddings take only less than half the space of vectors with 1024 dimensions
 * Vector Search is faster (less dimensions to compare)

* 134 MB (F32)
* 384 dims
* Time to embedd 12 docs (CPU only, AMD Ryzen 9 5950X): 1.1s
* `ollama pull znbang/bge:small-en-v1.5-f32`
* LangChain: `embeddings = OllamaEmbeddings(model="znbang/bge:small-en-v1.5-f32")`
