

# 🎯 Now Let’s Build Your Own Design System (SCSS Based)

We’ll structure it like a real design system.

# 📁 Folder Structure
```code
styles/
 ├── abstracts/
 │     _variables.scss
 │     _colors.scss
 │     _typography.scss
 │     _spacing.scss
 │     _mixins.scss
 │
 ├── base/
 │     _reset.scss
 │     _globals.scss
 │
 ├── components/
 │     _button.scss
 │     _card.scss
 │
 ├── layout/
 │     _grid.scss
 │     _container.scss
 │
 └── main.scss

```



# 🎨 1️⃣ Colors (Central Theme Control)

### styles/abstracts/_colors.scss
```scss
:root {  
  // Backgrounds  
  --color-bg-primary: #0B0F19;  
  --color-bg-secondary: #111827;  
  
  // Text  
  --color-text-primary: #E5E7EB;  
  --color-text-secondary: #9CA3AF;  
  
  // Accent  
  --color-accent-primary: #3B82F6;  
  --color-accent-secondary: #22C55E;  
  
  // Borders  
  --color-border: #1F2937;  
}
```

Now your entire theme is controlled from one file.

Want lighter theme later?  
Add `.light-theme {}` override.

---

# 🔤 2️⃣ Typography System

### styles/abstracts/_typography.scss
```scss

$font-primary: 'Inter', sans-serif;  
  
$font-sizes: (  
  h1: 3rem,  
  h2: 2.25rem,  
  h3: 1.75rem,  
  body-lg: 1.125rem,  
  body: 1rem,  
  small: 0.875rem  
);  
  
body {  
  font-family: $font-primary;  
  color: var(--color-text-primary);  
  background-color: var(--color-bg-primary);  
  line-height: 1.6;  
}  
  
h1 { font-size: map-get($font-sizes, h1); }  
h2 { font-size: map-get($font-sizes, h2); }  
h3 { font-size: map-get($font-sizes, h3); }
```

Now you have centralized typography control.

---

# 📏 3️⃣ Spacing System (8px Grid Discipline)

### styles/abstracts/_spacing.scss
```scss
$spacing-unit: 8px;  
  
@function spacing($multiplier) {  
  @return $spacing-unit * $multiplier;  
}
```

Usage:
```scss
.section {  
  padding: spacing(10) 0; // 80px  
}
```
Now you’re thinking like a design system engineer.

---

# 🧱 4️⃣ Grid System (Industrial Structure)

### styles/layout/_container.scss
```scss
.container {  
  max-width: 1200px;  
  margin: 0 auto;  
  padding: 0 spacing(4);  
}
```

### styles/layout/_grid.scss
```scss
.grid {  
  display: grid;  
  gap: spacing(6);  
}  
  
.grid-3 {  
  grid-template-columns: repeat(3, 1fr);  
}
```
---

# 🧩 5️⃣ Reusable Components

### Button Component
```scss
.button {  
  padding: spacing(2) spacing(4);  
  background-color: var(--color-accent-primary);  
  color: white;  
  border: none;  
  cursor: pointer;  
  font-weight: 600;  
  transition: opacity 0.2s ease;  
  
  &:hover {  
    opacity: 0.85;  
  }  
}
```
---

### Card Component
```scss
.card {  
  background-color: var(--color-bg-secondary);  
  padding: spacing(6);  
  border: 1px solid var(--color-border);  
}
```
Minimal.  
Structured.  
Industrial.

---

# 🎛 6️⃣ Theme Switching (Advanced But Elite)

Add:
```scss
.light-theme {  
  --color-bg-primary: #FFFFFF;  
  --color-text-primary: #111827;  
}
```
Then toggle class on `<body>`.

Now you have a theme engine.