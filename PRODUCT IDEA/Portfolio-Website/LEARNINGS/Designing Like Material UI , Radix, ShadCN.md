

## 🔍 Study These Libraries

- Material UI
    
- Radix UI
    
- shadcn/ui
    

They differ in philosophy:

| Library     | Style Philosophy              |
| ----------- | ----------------------------- |
| Material UI | Pre-styled, opinionated       |
| Radix       | Headless, accessibility-first |
| shadcn/ui   | Styled but composable         |



---

## 🧠 What They Do Differently

### 1️⃣ They Separate Logic From Style

**Radix:**

- Provides behavior only
    
- You provide styling
    

**Material UI:**

- Provides both behavior + style
    

You must decide your philosophy.

---

### 2️⃣ They Design for Scale

**They think:**

- Will this work in 500 screens?
    
- Can this be themed?
    
- Can this be overridden?
    
- Does it support dark mode?
    
- Is it accessible?
    

---

### 3️⃣ They Use Polymorphic Components

**Example:**
```TypeScript
<Button as="a" href="/home" />
```
**Instead of:**
```TypeScript
<Link><Button /></Link>
```

This is called the **Polymorphic "as" Pattern**.

---

### 4️⃣ They Use Design Tokens

**Instead of hardcoding:**
```scss
color: #0f172a;
```
**They use:**
```scss
color: var(--color-primary);
```
Central theme control.