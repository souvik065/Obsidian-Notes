

Here’s how it fits in your system:
```
Documents
   ↓
Chunking
   ↓
encode()  →  [vectors]
   ↓
Store in Vector DB

```


At query time:
```
User Query
   ↓
encode()
   ↓
Similarity Search
   ↓
Retrieve Top K Chunks

```