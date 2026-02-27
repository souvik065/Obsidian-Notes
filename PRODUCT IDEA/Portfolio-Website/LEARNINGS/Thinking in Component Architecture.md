
# 🏛 Thinking in Component Architecture

## 🧠 Layered Thinking

Instead of thinking:

> “I need a button.”

Think:

Level 1 — Primitive
- Box
- Text
- Stack

Level 2 — Composed Components
- Button
- Input
- Card

Level 3 — Patterns
- Form
- Modal
- Navbar

Level 4 — Layout Systems
- Dashboard layout
- Landing layout

Architecture = Layers.

---

## 🧱 Atomic Design Model

Atoms → Molecules → Organisms → Templates → Pages

Example:

Text (Atom)  
Button (Molecule)  
Navbar (Organism)  
Dashboard Template (Template)

This prevents chaos.

---

## 🧠 System Thinking Questions

Before building a component ask:

1. Is this reusable?
    
2. Should this be a primitive?
    
3. Is this part of a pattern?
    
4. Will this need variants?
    
5. Does it need theming?
    
6. Does it need accessibility support?