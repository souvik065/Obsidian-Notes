
## 🧠 What Does “API-like” Mean?

A component should feel like a **well-designed function API**, not random JSX.

**Bad:**
```Typescript
<div className="header-wrapper">  
  <div className="left-section">Logo</div>  
  <div className="right-section">Links</div>  
</div>
```
**Good:**
```Typescript
<Header>  
  <Header.Brand />  
  <Header.Nav />  
</Header>
```
It feels intentional. Structured. Predictable.

---

## 🎯 Goal

Design components so developers use them like:
```TypeScript
<Component>  
  <Component.Part />  
</Component>
```

Just like:

- `<Select><Select.Item /></Select>`
    
- `<Dialog><Dialog.Trigger /></Dialog>`


## 🧱 Core Concepts to Learn

### 1️⃣ Compound Component Pattern

Attach subcomponents to a parent:
```TypeScript
const Component = Object.assign(BaseComponent, {  
  SubPart,  
});
```
This enables:
```TypeScript
<Component>  
  <Component.SubPart />  
</Component>
```
---

### 2️⃣ Forwarding Refs

Always support:
```TypeScript
React.forwardRef()
```
Why?

- Focus control
- Animation libraries
- Accessibility
- Scroll control

Professional UI libraries always forward refs.

---

### 3️⃣ Extending Native HTML Props
```TypeScript

interface Props extends HTMLAttributes<HTMLDivElement> {}
```
Never rewrite default HTML props manually.

This makes your component:
- Flexible
- Extensible
- Accessible

---

## 🧩 API Design Checklist

When designing a component, ask:

- Is usage intuitive?
- Is naming semantic?
- Does it support composition?
- Does it support overrides?
- Does it forward refs?
- Is it accessible?