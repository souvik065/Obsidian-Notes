
# What is `dimension`?

`dimension` = size of each embedding vector.

**Example models:**
|Model|Dimension|
|---|---|
|all-MiniLM-L6-v2|384|
|text-embedding-3-small|1536|
|text-embedding-3-large|3072|

**If dimension = 384**

**Each text → vector of 384 numbers.**



### Why dimension is important in RAG?

Because:

1. Your vector database (Chroma, FAISS, Pinecone) must know dimension
    
2. Query embeddings must match document embeddings dimension
    
3. Similarity search requires same vector size



---
**Note:-**
If you mix dimensions:
`Error: dimension mismatch`