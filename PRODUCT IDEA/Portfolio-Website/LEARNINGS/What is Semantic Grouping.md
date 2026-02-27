

## 🧠 What is Semantic Grouping?

Grouping UI pieces by meaning, not styling.

Bad grouping:
```TypeScript
<CardLeft />  
<CardRight />
```
Semantic grouping:
```TypeScript
<Card>  
  <Card.Header />  
  <Card.Body />  
  <Card.Footer />  
</Card>
```

This mirrors human understanding.

---

## 🎯 Why It Matters

- Improves readability
- Self-documenting structure
- Easier scaling
- Clear hierarchy

---

## 🧱 Techniques

### 1️⃣ Compound Components

Used for grouping related parts.

### 2️⃣ React Context (Advanced)

For shared state inside group:
```TypeScript
<Tabs>  
  <Tabs.List />  
  <Tabs.Trigger />  
  <Tabs.Content />  
</Tabs>
```

Internally uses:
```TypeScript
const TabsContext = createContext()
```
This avoids prop drilling.

---

## 🧠 Mental Model

Think in terms of:
- Container
- Sub-parts
- Internal communication
- External API

Not random divs.