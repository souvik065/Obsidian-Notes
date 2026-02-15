


In RAG, 
	**embeddings convert text → vector numbers.**


**Example:**
```
"RAG is powerful"
```

**becomes:**
```
[0.234, -0.992, 0.111, 0.444, ...]
```

**This numeric representation captures semantic meaning.**



### 🔹 `encode()` in embedding pipeline

`def encode(self, texts: List[str]) -> np.ndarray:`

**This function:**
1. Takes multiple texts
    
2. Sends them to embedding model
    
3. Returns matrix of vectors