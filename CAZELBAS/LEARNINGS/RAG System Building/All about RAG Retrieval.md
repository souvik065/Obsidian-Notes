
# 1. What Retrieval Really Is (First Principles)
RAG = **Retrieval Augmented Generation**

The LLM is NOT the knowledge source.  
Your **retriever is the knowledge selector**.

Think like this:

LLM = brain  
Vector DB = library  
Retriever = librarian

If the librarian gives wrong books → brain answers wrong.

So retrieval is:

> Given a query Q, find the most relevant chunks from a knowledge base K.

Mathematically:
```
Input: query q
Corpus: D = {d1, d2, d3, ..., dn}
Output: Top-k relevant documents
```



---

# 2. Two Fundamental Types of Retrieval

There are only **two core paradigms**.

## 🔹 1. Sparse Retrieval (Lexical)

Old-school method.

Matches exact words.

Example:

- Query: "neural network optimization"
    
- It finds documents containing those words.
    

### Algorithms:

- Apache Lucene
    
- Elasticsearch
    
- BM25
    

### BM25 Idea

Score based on:
- Term frequency
    
- Inverse document frequency
    
- Document length normalization
    

Good for:

- Legal documents
    
- Keyword-heavy search
    
- Exact matching needed
    

Weakness:

- Doesn’t understand meaning.
---
## 🔹 2. Dense Retrieval (Semantic Retrieval)

Modern RAG uses this.

Instead of words → convert text into **vectors**.

### Steps:

1. Use embedding model
    
2. Convert query → vector
    
3. Convert documents → vectors
    
4. Compute similarity
    
5. Return top-k
    

Popular embedding models:

- OpenAI embeddings
    
- Hugging Face sentence transformers
    
- all-MiniLM-L6-v2


---

# 3. Mathematical Core of Retrieval

## 🔹 Vector Representation

Each text → high dimensional vector

Example:
```arduino
"neural network" → [0.12, -0.44, 0.91, ...]

```

Dimension might be:

- 384
    
- 768
    
- 1536
## 🔹 Similarity Search

Most common:

### 1️⃣ Cosine Similarity

cos(θ)=A⋅B∣∣A∣∣∣∣B∣∣cos(\theta) = \frac{A \cdot B}{||A|| ||B||}cos(θ)=∣∣A∣∣∣∣B∣∣A⋅B​

Measures angle similarity.

Why normalization matters:  
If vectors are normalized:

cos(A,B)=A⋅Bcos(A, B) = A \cdot Bcos(A,B)=A⋅B

So search becomes just dot product.

---

### 2️⃣ Dot Product

Used in many ANN systems.

---

### 3️⃣ Euclidean Distance

Less common in RAG.

---


# 4. ANN (Approximate Nearest Neighbor)

If you have 1M vectors, brute force search is slow.

So we use ANN indexes.

Popular libraries:

- FAISS
    
- HNSW
    
- Annoy
    

### HNSW Idea

Hierarchical small-world graph.

Search becomes:

- Start at top layer
    
- Navigate closer to query vector
    
- Move down layers



---


# 5. Types of Retrieval in RAG Systems

Now we go deeper.

---

## 🔹 1. Basic Top-k Retrieval

Just return k nearest chunks.

Simple.  
Baseline.

---

## 🔹 2. Hybrid Retrieval

Combine:

Sparse (BM25) + Dense (Embeddings)

Why?  
Some queries need exact keyword match.  
Some need semantic similarity.

Hybrid = best of both worlds.

Example:  
Elasticsearch + FAISS together.

---

## 🔹 3. Multi-Query Retrieval

Instead of 1 query:

Generate multiple paraphrases:

- “What is backpropagation?”
    
- “How does gradient descent update weights?”
    

Retrieve for each.  
Merge results.

Improves recall.

---

## 🔹 4. Query Expansion

Add related keywords before searching.

---

## 🔹 5. Re-ranking Retrieval

Two-stage system:

1. Retriever → gets top 50
    
2. Cross-encoder → reranks to top 5
    

Cross encoder models:

- Microsoft MiniLM cross encoders
    
- Google BERT cross encoders
    

Retriever = fast  
Reranker = accurate

This is production-level RAG.

---

## 🔹 6. Parent-Child Retrieval

Chunk small.  
But store reference to full document.

Retrieve small chunk.  
Feed full parent document.

Prevents context fragmentation.

---

## 🔹 7. Metadata Filtering

Filter before similarity search.

Example:

`department = "finance" year > 2022`

This is critical in enterprise RAG.

---

## 🔹 8. Semantic Chunking Retrieval

Instead of fixed 500 tokens:  
Chunk based on meaning boundaries.

Improves retrieval quality.


---


# 6. How Retrieval Pipeline Works (Implementation View)

Now let’s design it like an engineer.

---

## Step 1 — Data Ingestion

- Load PDFs / JSON / Markdown
    
- Clean text
    
- Chunk
    
- Add metadata
    

---

## Step 2 — Embedding Creation

For each chunk:

`vector = embedding_model.encode(chunk)`

Store:

`{   id,   vector,   metadata,   text }`

---

## Step 3 — Indexing

Insert into:

- FAISS
    
- HNSW
    
- Vector DB
    

Popular vector DBs:

- Pinecone
    
- Weaviate
    
- Milvus
    

---

## Step 4 — Query Time

User asks:

`"What is gradient descent?"`

Pipeline:

1. Embed query
    
2. Search ANN index
    
3. Retrieve top-k
    
4. Optional rerank
    
5. Inject into LLM prompt




# 7. How to Implement Retrieval Practically (Minimal Version)

If you are building local RAG (like your Local AI Engine project), do this:

### Minimal Stack:

- sentence-transformer
    
- FAISS
    
- cosine similarity
    

Pipeline:
```python

`embeddings = model.encode(chunks) index = faiss.IndexFlatIP(dimension) index.add(embeddings)  query_vector = model.encode([query]) scores, indices = index.search(query_vector, k=5)`
```
That’s retrieval.


# 8. How to Evaluate Retrieval Quality

This is advanced but important.

Metrics:

- Recall@k
    
- Precision@k
    
- MRR (Mean Reciprocal Rank)
    

In RAG, recall matters more than precision.  
Because LLM can filter, but cannot invent missing info.


---
# 9. Advanced Production Concepts

Now real engineering.

---

## 🔹 Embedding Normalization

Always normalize vectors if using cosine similarity.

---

## 🔹 Batch Encoding

Batch size impacts:

- Memory
    
- Throughput
    
- GPU utilization
    

---

## 🔹 Cold Start Problem

Embedding model must be domain-aligned.

Medical RAG?  
Use biomedical embedding model.

---

## 🔹 Caching

Cache:

- Query embeddings
    
- Retrieved chunks
    

Reduces latency.



---

You must deeply understand:

1. Linear algebra (dot product geometry)
    
2. Information retrieval theory (BM25)
    
3. ANN indexing
    
4. Embedding training objective
    
5. Evaluation metrics