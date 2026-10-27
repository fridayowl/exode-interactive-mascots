# 220+ Free Interactive Runtime Mascots (Rigged 3D & 2D Characters)

<p align="center">
  <a href="https://fridayowl.github.io/exode-interactive-mascots/"><img src="https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-ff5a36.svg?style=for-the-badge&logo=github" alt="Live Demo" /></a>
  <a href="https://github.com/fridayowl/exode-interactive-mascots/stargazers"><img src="https://img.shields.io/github/stars/fridayowl/exode-interactive-mascots?style=for-the-badge&logo=star&color=f59e0b" alt="GitHub Stars" /></a>
  <a href="https://github.com/fridayowl/exode-interactive-mascots/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-10b981.svg?style=for-the-badge" alt="License" /></a>
  <img src="https://img.shields.io/badge/Mascots-220%2B%20Free-6366f1.svg?style=for-the-badge" alt="220+ Mascots" />
  <img src="https://img.shields.io/badge/Commercial%20Use-100%25%20Free-0ea5e9.svg?style=for-the-badge" alt="Free for Commercial Use" />
</p>

<p align="center">
  <strong>A free, open-source collection of 220+ interactive, physics-driven runtime mascots for web, desktop, and mobile applications.</strong><br>
  Built with real-time bone rigging, mouse/cursor gaze tracking, 17 expressive micro-interaction moments, and zero external dependencies. Powered by <a href="https://www.exodeui.com">ExodeUI</a>.
</p>

<p align="center">
  <a href="https://fridayowl.github.io/exode-interactive-mascots/"><strong>Explore 220+ Mascots Live Playground &rarr;</strong></a> |
  <a href="https://www.exodeui.com/mascots"><strong>ExodeUI Mascots Platform</strong></a> |
  <a href="https://app.exodeui.com"><strong>Open Exode Studio</strong></a>
</p>

---

## ⭐ If you like this project, please give it a star on GitHub! It helps more developers and designers find free open-source character animations.

---

## 🌟 Why Exode Interactive Mascots?

| Feature | Static SVG / Avatars | Heavy 3D (Three.js / Spline) | **Exode Runtime Mascots** |
| :--- | :--- | :--- | :--- |
| **Interactivity** | ❌ None (Static) | ⚠️ High GPU/CPU overhead | ✅ **Cursor gaze tracking & natural physics** |
| **File Size** | ~10 KB | 5 MB – 25 MB+ | ✅ **Only ~13 KB per character (`.bexode`)** |
| **Animation Moments** | ❌ None | ⚠️ Pre-baked timeline clips | ✅ **17 live moments (wave, party, laugh, love...)** |
| **Tuning & Recoloring**| ❌ Difficult | ⚠️ Re-bake shaders & textures | ✅ **Live mood, head tilt, ear perk & palette mixer** |
| **Embed Simplicity** | `<img src="...">` | Complex Canvas + Scene setup | ✅ **Drop-in `<exode-mascot>` web component** |
| **Licensing** | Mixed | Paid subscriptions / seats | ✅ **100% Free & Open Source for Commercial Use** |

---

## ✨ Features

- **220+ Ready-to-Use Characters**: Cats, Foxes, Bunnies, Bears, Robots, Dogs, Pandas, Dragons, Ghosts, Penguins, Lions, Aliens, Owls, Axolotls, Koalas, Ducks, Seals, Otters, and more.
- **Natural Cursor Tracking**: Characters look toward and track the user's cursor or touch pointer in real time with subtle organic head sways.
- **17 Interactive Emotional Moments**:
  `wave`, `party`, `cool`, `love`, `laugh`, `jump`, `smile`, `sleepy`, `bounce`, `wink`, `surprise`, and more.
- **Dynamic Parameter Controls**:
  - `mood`: `0` (sleepy) &rarr; `50` (neutral) &rarr; `100` (joyful)
  - `tilt`: `-100` (left tilt) &rarr; `+100` (right tilt)
  - `ears`: `0` (flat) &rarr; `100` (perked up)
- **Live Brand Recoloring**: Dynamically swap character, accent, and background colors with real-time lighting calculation.
- **Multi-Framework Support**: Works with standard HTML, React, Next.js, Vue 3, Svelte, Angular, and vanilla JavaScript.

---

## 🚀 Quick Start

### 1. Vanilla HTML / Web Component (Easiest)

Add the lightweight runtime script to your page, then place `<exode-mascot>` anywhere:

```html
<!-- 1. Load the runtime (~140 KB gzipped, cached) -->
<script src="https://fridayowl.github.io/exode-interactive-mascots/exode-mascot.js" defer></script>

<!-- 2. Place any character by ID -->
<exode-mascot mascot="ip-3001" style="width: 200px; height: 200px;"></exode-mascot>

<!-- Custom mood, tilt, and colors -->
<exode-mascot 
  mascot="ip-3002" 
  mood="90" 
  tilt="15" 
  ears="80" 
  colors="#f28a3c,#fbf7ef,#28344f"
  style="width: 240px; height: 240px;"
></exode-mascot>
```

### 2. JavaScript Interaction API

Control your mascot programmatically based on app events:

```javascript
const mascot = document.querySelector('exode-mascot');

// Trigger any emotional moment
mascot.play('wave');   // 'party', 'cool', 'love', 'laugh', 'jump', etc.

// Adjust expression on the fly
mascot.set('mood', 100);  // 0 to 100
mascot.set('tilt', 20);   // -100 to 100

// Dynamic brand recolor
mascot.recolor({
  main: '#72b8f0',
  second: '#fbf7ef',
  bg: '#e6f0fb'
});
```

### 3. React / Next.js

```tsx
import React, { useRef } from 'react';
import Script from 'next/script';

export function InteractiveAssistant() {
  const mascotRef = useRef<any>(null);

  const handleCelebrate = () => {
    mascotRef.current?.play('party');
  };

  return (
    <div>
      <Script 
        src="https://fridayowl.github.io/exode-interactive-mascots/exode-mascot.js" 
        strategy="afterInteractive" 
      />
      <exode-mascot
        ref={mascotRef}
        mascot="ip-3005"
        mood="85"
        tilt="0"
        ears="90"
        style={{ width: 220, height: 220 }}
      />
      <button onClick={handleCelebrate}>Celebrate!</button>
    </div>
  );
}
```

### 4. Vue 3 / Nuxt

```vue
<template>
  <div class="mascot-wrapper">
    <exode-mascot 
      ref="mascotEl"
      mascot="ip-3001" 
      mood="90" 
      style="width: 200px; height: 200px;" 
    />
    <button @click="celebrate">Wave Hello</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import 'https://fridayowl.github.io/exode-interactive-mascots/exode-mascot.js';

const mascotEl = ref(null);
const celebrate = () => mascotEl.value?.play('wave');
</script>
```

---

## 🐾 Available Mascot Species (30 Animals & Characters)

The collection includes 221 unique variations across 30 character types:

- **Cat** (12) • **Fox** (12) • **Bunny** (12) • **Bear** (11) • **Dog** (8) • **Robot** (2)
- **Dragon** (1) • **Panda** (8) • **Ghost** (1) • **Penguin** (7) • **Lion** (7) • **Alien** (1)
- **Owl** (9) • **Axolotl** (10) • **Koala** (7) • **Duck** (7) • **Seal** (7) • **Sheep** (6)
- **Raccoon** (8) • **Fawn** (8) • **Otter** (8) • **Pup** (6) • **Pig** (8) • **Chick** (6)
- **Monkey** (6) • **Hamster** (7) • **Mouse** (9) • **Cow** (8) • **Frog** (10) • **Whale** (9)

---

## 🎨 Online Interactive Playground

Test and customize all 220+ mascots live in your browser:  
👉 **[https://fridayowl.github.io/exode-interactive-mascots/](https://fridayowl.github.io/exode-interactive-mascots/)**

- Search by animal species or name
- Tune sliders for mood, tilt, and ears
- Trigger interactive moments with immediate visual feedback
- Copy ready-to-paste component code for HTML, React, Vue, and Svelte
- One-click `.bexode` binary file downloads

---

## 🏷️ Keywords & Search Topics

`interactive-mascots` • `animated-mascots` • `free-mascots` • `character-animation` • `open-source-characters` • `react-mascots` • `3d-mascots` • `ui-avatars` • `web-components` • `gamification` • `micro-interactions` • `spring-physics` • `vector-rigging` • `vue-mascots` • `svelte-characters` • `exodeui`

---

## 📄 Open Source License

- Interactive mascot characters, rigging, and runtime definitions are licensed under the **[MIT License](https://opensource.org/licenses/MIT)**.
- **100% Free for both Personal and Commercial Use.**
- Powered by the [ExodeUI Motion Platform](https://www.exodeui.com). A ⭐ star on GitHub is greatly appreciated!

---

<p align="center">
  Crafted with care by the <a href="https://www.exodeui.com">ExodeUI</a> team &bull; <a href="https://github.com/fridayowl/exode-interactive-mascots">GitHub Repository</a>
</p>
