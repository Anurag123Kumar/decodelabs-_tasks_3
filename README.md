# DecodeLabs — Frontend Project 3: Interactive Web Elements ⚡

> **Industrial Training Kit · Batch 2026 · Powered by DecodeLabs**

A fully interactive, JavaScript-powered webpage built as the third milestone of the DecodeLabs frontend internship programme. This project moves beyond static layouts into **User Experience** — engineering the client-side nervous system through DOM manipulation, event listeners, and state management.

---

## 📋 Project Overview

| Field       | Details                                  |
|-------------|------------------------------------------|
| **Project** | Project 3 — Interactive Web Elements    |
| **Batch**   | 2026                                     |
| **Track**   | Frontend Development                     |
| **Goal**    | Add interactivity to a webpage using JavaScript |
| **Builds on** | Project 2 (Responsive Web Layout)     |

---

## 🗂️ File Structure

```
project-3/
├── index.html      # Semantic HTML5 + all inline JavaScript
├── style.css       # Mobile-first CSS with dark mode + JS state classes
└── README.md       # This file
```

---

## ✅ Implementation Checklist

All six requirements from the project brief are implemented:

- [x] **DOM Selection & Manipulation** — `querySelector`, `textContent`, `classList` to read and update elements
- [x] **Event Listeners** — `addEventListener` on clicks, keyboard input, and page scroll
- [x] **State Management** — UI state tracked with `let` variables; DOM always reflects current state
- [x] **Dynamic Content Updates** — Content updates without reload using `textContent` (XSS-safe)
- [x] **Dark Mode Toggle** — Theme toggle via `classList.toggle()` on `document.documentElement`
- [x] **Engineering Standards: Decoupling** — `js-` prefix for hooks, `is-` prefix for visual state

---

## ⚡ Interactive Features

### Dark Mode Toggle
A theme button in the header toggles the `data-theme="dark"` attribute on `<html>`. All colour changes are driven purely by CSS custom property overrides under `[data-theme="dark"]` — JavaScript handles only the state flip.

### Flip Cards (Skills Section)
Each skill card is clickable and flips 180° to reveal a code snippet on the back. Implemented with `classList.toggle('is-flipped')` and a CSS 3D transform.

### Counter Widget (Demo 01)
A classic IPO loop: increment / decrement / reset buttons mutate a `counterValue` state variable and call `renderCounter()` to update the display. The number changes colour based on positive, negative, or zero state.

### Theme Color Picker (Demo 02)
Clicking a colour swatch reads `dataset.color` and calls `document.documentElement.style.setProperty()` to update the `--clr-accent` CSS variable live across the entire page.

### Live Character Counter (Demo 03)
An `input` event listener on a `<textarea>` reads `.value.length` and updates a counter display in real time. Warning and danger classes are toggled at 80% and 95% of the 200-character limit.

### Quote Generator (Demo 04)
A button picks a random entry from a hardcoded array using `Math.floor(Math.random())`, with deduplication logic to prevent the same quote appearing twice in a row. Content is injected via `textContent` (not `innerHTML`) per the XSS safety standard from the brief.

### Progress Checklist
Six built-in requirements plus a custom task adder. Custom tasks are built entirely with `document.createElement()` and `appendChild()` — no HTML templates. A progress bar and counter update on every check/uncheck action.

### FAQ Accordion
A single-open accordion where clicking a trigger toggles `.is-open` on the parent item, updates `aria-expanded`, and sets `panel.hidden`. Clicking an already-open item collapses it.

### Scroll Reveal
`IntersectionObserver` adds `.is-visible` to demo cards, checklist items, and skill cards as they enter the viewport, triggering CSS entrance animations.

### Stat Counters
Three live stat boxes in the About section track page visits (via `sessionStorage`), total clicks (a document-level listener), and completed tasks — all updated in real time.

---

## 🧠 Core JavaScript Concepts Applied

### The IPO Loop
Every interactive element in this project follows the **Input → Process → Output** model taught in the brief:

| Stage | Role | Example |
|-------|------|---------|
| **Input** | An event fires | User clicks a button |
| **Process** | Logic runs | State variable is mutated |
| **Output** | DOM is updated | `textContent` / `classList` changes |

### Variable Integrity
| Declaration | Reassignment | Scope | Usage in this project |
|-------------|-------------|-------|-----------------------|
| `const` | No | Block | All DOM references |
| `let` | Yes | Block | All mutable state (counters, flags) |
| `var` | — | — | Not used |

### Engineering Standards: Decoupling

```html
<!-- Fragile (avoid) -->
<button class="submit-btn active">

<!-- Robust (used throughout) -->
<button class="btn-primary js-checkout is-loading">
```

- `js-` prefix: JavaScript hooks only, never styled via CSS
- `is-` prefix: Visual state only (`.is-active`, `.is-open`, `.is-done`, `.is-flipped`)

---

## 🎨 CSS Architecture

The stylesheet extends Project 2 with the following additions:

**Dark mode** via `[data-theme="dark"]` attribute overrides on CSS custom properties — zero JavaScript style manipulation, only class/attribute toggling.

**JS state classes** drive all animations and transitions:

| Class | Trigger | Effect |
|-------|---------|--------|
| `.is-flipped` | Card click | 3D flip transform |
| `.is-open` | Accordion click | Panel reveal |
| `.is-done` | Checklist check | Strike-through + muted opacity |
| `.is-active` | Swatch click | Scale + ring highlight |
| `.is-positive / .is-negative` | Counter change | Green / red text colour |
| `.is-warning / .is-danger` | Char count threshold | Amber / red counter text |
| `.is-visible` | IntersectionObserver | Fade-in slide entrance |
| `.is-animating` | Quote change | Fade-out / fade-in |
| `.is-error` | Empty task submit | Red shake on input |

---

## 🚀 Getting Started

No build tools or dependencies required.

1. Clone or download the project files
2. Open `index.html` in any modern browser
3. Try every interactive element — counter, color picker, dark mode, accordion, checklist

---

## 📚 Resources Referenced

- [MDN Web Docs — Document.querySelector](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
- [MDN Web Docs — EventTarget.addEventListener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
- [MDN Web Docs — Element.classList](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList)
- [MDN Web Docs — IntersectionObserver](https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver)
- [MDN Web Docs — CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)

---

## 📬 Contact

| Channel | Details |
|---------|---------|
| 📞 Phone | +91 89330 06408 |
| ✉ Email | decodelabs.tech@gmail.com |
| 🌎 Web | [www.decodelabs.tech](https://www.decodelabs.tech) |
| 📍 Location | Greater Lucknow, India |

---

© 2026 DecodeLabs. All rights reserved.
