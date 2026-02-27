
# What Retrieval Means in RAG

In a **Retrieval-Augmented Generation (RAG)** system:

- **LLM = generator**
    
- **Retriever = memory search engine**
    

Retrieval is the system that:

> Finds the most relevant pieces of external knowledge for a given query.

Instead of the LLM guessing from its training data, we:

1. Search a knowledge base
    
2. Pull relevant chunks
    
3. Inject them into the prompt
    
4. Let the LLM generate grounded answers

---
# High-Level Retrieval Pipeline

Retrieval includes:
```
User Query
   ↓
Query Processing
   ↓
Embedding / Encoding
   ↓
Similarity Search
   ↓
Ranking / Re-ranking
   ↓
Top-k Document Chunks
```



---

# Step-by-Step Breakdown of Retrieval

## 🔹 A. Indexing Phase (Offline)

Before retrieval works, you must prepare the knowledge base.

### 1. Chunking

Split documents into chunks:

- Sentence-based
    
- Token-based
    
- Character-based
    
- Semantic chunking
    

Why?

Because embeddings work better on smaller coherent text.

Example:
```
Document → 1000 words
Split → 200-word chunks
```

### 2. Embedding the Chunks

Each chunk → converted into a vector using embedding model.

Example:

- Sentence Transformers
    
- OpenAI embeddings
    
- BGE models
    

Result:
```
Chunk A → [0.12, -0.93, 0.44, ..., 0.01] (768-d vector)
Chunk B → [0.77, 0.11, -0.28, ..., -0.66]
```

These vectors live in high-dimensional semantic space.

### 3. Store in Vector Database

Stored in:

- FAISS
    
- Chroma
    
- Weaviate
    
- Pinecone
    

These systems optimize **approximate nearest neighbor (ANN)** search.

## 🔹 B. Query Phase (Online Retrieval)

Now user asks:

> "What is gradient descent?"

---

### 1️⃣ Query Embedding

The query is converted into a vector using the SAME embedding model.
```
Query → [0.09, -0.91, 0.39, ..., 0.02]
```
Important rule:

> Query embedding model MUST match document embedding model.

---

### 2️⃣ Similarity Search

Now we compute similarity between:
```
Query vector  
vs  
All chunk vectors
```
Most common metric:

### Cosine Similarity
$$
\text{cosine}(A, B) = \frac{A \cdot B}{||A|| ||B||}
$$​

This measures angle similarity, not magnitude.

Why cosine?  
Because semantic meaning depends on direction in vector space.

### 3️⃣ Top-K Retrieval

Return:
```
Top 5 most similar chunks
```

This is called:

> Dense Retrieval


# 4️⃣ Types of Retrieval in RAG

Now we go deeper.
## 🔹 1. Sparse Retrieval (Traditional IR)

Old-school search like:

- TF-IDF
    
- BM25
    

Used by search engines like **Google** (early versions)

It matches keywords, not meaning.

Example:

Query: "bank interest rate"

Matches documents containing:

- bank
    
- interest
    
- rate
    

Does not understand semantics.

---

## 🔹 2. Dense Retrieval (Vector-Based)

Modern semantic retrieval.

Used in:

- Chroma
    
- FAISS
    
- Pinecone
    

Understands meaning, not just words.

---

## 🔹 3. Hybrid Retrieval (Best in Production)

Combine:

Sparse score + Dense score

Why?

Because dense models may miss:

- Exact keywords
    
- Numbers
    
- Code
    
- Proper nouns
    

Hybrid improves recall + precision.

---

## 🔹 4. Multi-Vector Retrieval

Instead of:
```
1 chunk = 1 vector
```
We store:
```
1 chunk = multiple vectors
```
Example:

- ColBERT-style late interaction models
    

Improves accuracy but increases compute.

---

## 🔹 5. Re-ranking (Second Stage Retrieval)

After retrieving top 20 candidates:

Use a cross-encoder model to re-score.

This gives better ranking quality.

Pipeline:
```
ANN Search → Top 20  
Cross-Encoder → Re-rank  
Return Top 5
```

---

# 5️⃣ What Retrieval Actually Optimizes

Retrieval tries to maximize:

### 🔹 Recall

Did we retrieve the correct chunk at all?

### 🔹 Precision

Are retrieved chunks actually relevant?

### 🔹 MRR (Mean Reciprocal Rank)

How high is the correct document ranked?

---

# 6️⃣ Important Retrieval Nuances (Advanced)

Now we go into real engineering depth.

---

## ⚡ 1. Embedding Normalization

Before storing vectors:
$$
v = \frac{v}{||v||}​
$$
Why?

Because cosine similarity becomes dot product after normalization.

Speeds up ANN search.

---

## ⚡ 2. Approximate Nearest Neighbor (ANN)

We cannot compare with millions of vectors directly.

So we use:

- HNSW
    
- IVF
    
- PQ (Product Quantization)
    

These trade small accuracy loss for huge speed gain.

---

## ⚡ 3. Chunk Size Tradeoff

Small chunks:

- Better precision
    
- Worse context continuity
    

Large chunks:

- Better context
    
- Worse similarity resolution
    

Sweet spot:  
150–400 tokens (depends on domain)

---

## ⚡ 4. Query Expansion

Improve retrieval by:

- Synonym expansion
    
- LLM rewriting query
    
- Multi-query retrieval
    

Example:

Original:  
"What is backpropagation?"

Expanded:  
"How does backpropagation work in neural networks?"

Improves recall.

---

## ⚡ 5. Metadata Filtering

Sometimes you filter BEFORE similarity search:

Example:

- Only search documents from 2024
    
- Only search finance category
    

This reduces noise.

---

## ⚡ 6. Retrieval Failure Modes

Common issues:

1. Embedding model mismatch
    
2. Poor chunking
    
3. Too small top-k
    
4. Domain mismatch
    
5. Query too vague
---

# 7️⃣ Full Retrieval Architecture (Production Grade)

Real production RAG retrieval looks like:
```
User Query
   ↓
Query Rewriter (LLM)
   ↓
Hybrid Retriever (Sparse + Dense)
   ↓
ANN Search
   ↓
Metadata Filtering
   ↓
Cross-Encoder Re-ranker
   ↓
Top-k Context
   ↓
LLM Generation

```


---

# 8️⃣ Mathematical View

Let:

- D = set of document vectors
    
- q = query vector
    

Retrieval solves:
$$
\arg\max_{d \in D} sim(q, d)
$$
Where sim = cosine or dot product.

---

# 9️⃣ Why Retrieval is Harder Than Generation

LLMs hallucinate if retrieval is bad.

If retrieval fails:

- Generation cannot fix it.
    

Garbage retrieval → garbage generation.

So:

> Retrieval quality determines RAG reliability.


---

# 🔟 Deep Insight (Very Important)

Retrieval is fundamentally:

> Learning a good vector space where semantic similarity = geometric closeness.

If embeddings are poor → no retrieval trick can fix it.


---




# 1️⃣1️⃣ If You Want Mastery

Since you're building RAG systems:

You should deeply understand:

1. Cosine similarity math
    
2. Vector normalization
    
3. HNSW indexing
    
4. Cross-encoders vs bi-encoders
    
5. Hybrid search scoring
    
6. Chunking experiments
    
7. Retrieval evaluation metrics




---
Source : ChatGPT 23mcab03@kristujayanti.com
[Chat1](https://chatgpt.com/c/69a14207-9910-8324-8594-d811aabffc3e)
