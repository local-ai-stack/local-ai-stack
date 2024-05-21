Embedding Models for the Local AI Stack
=======================================
Typically, you want a specialized embedding model to create the vector embeddings for documents.

How to run an embedding model
-----------------------------
Some options:

* Ollama: Ollama can also run embedding models (not "just" LLMs) 
* https://github.com/huggingface/text-embeddings-inference
* [SentenceTransformers](https://www.sbert.net/index.html): Sentence Embeddings using Siamese BERT-Networks
* [FastEmbedd](https://github.com/qdrant/fastembed): Python lib running the ONNX Runtime;
  claims to be fast and lightweight. CPU and GPU editions.

Options for resource-constrained devices:

* TensorFlow Lite offers [text embedders](https://www.tensorflow.org/lite/inference_with_metadata/task_library/text_embedder),
  e.g. universal-sentence-encoder-qa-ondevice

Dimensionality
--------------
Embedding models produce vectors of a specific dimensionality.
For example, a dimensionality of 512 indicates that one vector consists of 512 values of a primitive type like float.
While larger embedding models often come with a higher dimensionality, smaller dimensionality can also have advantages.

For example, when comparing 384 vs. 1024 dimensions:

* Embeddings with 384 dimensions take only 38% the space of vectors with 1024 dimensions.
* Vector Search is faster (less dimensions to compare)

This may become be significant if you store a lot of documents.

Embedding models well suited for local AI
-----------------------------------------
Here are some selected embedding models for English that offer a great quality per size ratio.
We start with the larger ones and proceed to the smaller ones.

### mxbai-embed-large

* 670 MB (F16)
* 1024 dimensions
* MTEB average score (higher is better): 64.68
* Time to embedd 12 docs (CPU only, AMD Ryzen 9 5950X): 2.2s
* `ollama pull mxbai-embed-large`
* LangChain: `embeddings = OllamaEmbeddings(model="mxbai-embed-large")` 

### bge-small-en-v1.5

Twice as fast as mxbai-embed-large and uses much lower resources.
Quality seems fine for e.g. testing; did not investigate real use cases yet.

* 134 MB (F32)
* 384 dimensions
* MTEB average score (higher is better): 62.17
* Time to embedd 12 docs (CPU only, AMD Ryzen 9 5950X): 1.1s
* `ollama pull znbang/bge:small-en-v1.5-f32`
* LangChain: `embeddings = OllamaEmbeddings(model="znbang/bge:small-en-v1.5-f32")`

### all-MiniLM-L6-v2

[all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) is part of
the sentence transformer collection ([SBERT](https://www.sbert.net/)).
For it's relatively small size, it is still quite good.

* 90 MB (F32), 46 MB (F16)
* 384 dimensions
* MTEB average score (higher is better): 56.26

Embedding model comparisons
---------------------------

### Huggingface MTEB leaderboard

The [MTEB leaderboard](https://huggingface.co/spaces/mteb/leaderboard) gives a good first impression of available embedding models.
It comes with quality scores, model sizes, memory requirements and vector dimensions.