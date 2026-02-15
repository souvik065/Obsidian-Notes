

# Why This Design is Clean (Software Architecture View)

Since you're building a RAG library, this abstraction allows:
```python
def build_vector_store(provider: EmbeddingProvider):
    vectors = provider.encode(texts)

```


It doesn’t care whether provider is:
- OpenAI
- Ollama
- HuggingFace
- Custom local model
That’s good architecture.


---

# 🔥 Simple Analogy

Think of `EmbeddingProvider` as:

> “Any machine that converts text → vectors”

It doesn’t care which machine.  
It just enforces:

- You must have `encode()`
    
- You must tell me vector `dimension`
    
- You must tell me `model_name`