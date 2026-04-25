# 🛡️ ClayScripts | Interactive Script Portfolio

Welcome to the **ClayScripts Interactive Script Portfolio**. This repository serves as a high-fidelity, web-based showcase for my FiveM development projects, specifically highlighting the advanced **`cl_idcard` NUI System**.

This project is more than just a static website; it is a fully functional engineering sandbox that simulates the complex bridge between a game server (Lua) and a web frontend (JavaScript) directly in your browser.

## ✨ Live Demo
🌐 **[View the Live Portfolio](https://clayscripts-fivem.github.io/script-portfolio/)** *(Adjust domain if hosted under an Organization)*

---

## 🏗️ Architecture & Technical Highlights

This showcase is engineered to demonstrate best practices in **Performance, Security, and Modularity**.

### 1. GPU-Accelerated 3D Rendering Engine
The interactive ID/Passport preview runs smoothly at 60fps. All CSS 3D transforms (`rotateY`, `perspective`) are offloaded to the GPU. A custom `requestAnimationFrame` pipeline prevents browser layout-thrashing during intense mouse-move operations.

### 2. FiveM Lua <-> JS Bridge Simulation
In a real FiveM environment, the NUI receives state updates via `SendNUIMessage`. This portfolio perfectly simulates that architecture by using React to generate complex JSON payloads and injecting them dynamically into the NUI iframe, bypassing the need for a live game server.

### 3. Safe-DOM Injection & XSS Protection
To prevent Code-Injection (which is a common vulnerability in FiveM UI's when handling unverified player names), the underlying NUI logic uses a strict Node-Text-Injector system that filters out dangerous HTML tags before mounting data to the DOM.

### 4. ICAO-Standard MRZ Calculation
The Machine Readable Zone (MRZ) on the passport is not static. It is generated dynamically via a custom algorithm that parses input data, formats dates, and pads strings to strictly comply with the international 39-character width ISO standard.

### 5. Asynchronous Asset-Resolver Pipeline
Player avatars and seals are loaded asynchronously via Promises. If a URL is unavailable (e.g., a broken Discord avatar link), the system gracefully falls back to a placeholder icon without blocking the NUI render pipeline.

### 6. IP Protection & Build Pipeline
To protect the intellectual property of the NUI logic:
- The core JavaScript logic (`script.js`) is heavily protected using **Control-Flow Flattening, Dead Code Injection, and Base64 String Encoding**.
- The CSS and HTML are compressed into strict "Safe-Mode" single-line strings.
- Only the `dist` folder is intended for public GitHub Pages deployment.

---

## 🛠️ Tech Stack

* **Core Framework:** React 18 + Vite
* **Styling:** Modern Vanilla CSS (Glassmorphism, Flexbox/Grid Layouts, CSS Variables)
* **NUI Engine:** Vanilla ES6 JavaScript (No heavy frameworks inside the NUI to prevent memory leaks in-game)
* **Icons:** Lucide React
* **Build Tools:** Vite Build, HTML-Minifier-Terser, Clean-CSS, JavaScript-Obfuscator

---

---

## 🔒 Security & Deployment

This repository serves strictly as a **production-ready showcase**. 
To protect intellectual property and prevent unauthorized use of the NUI logic:
- The core JavaScript logic is heavily protected using advanced Control-Flow Flattening and String Encoding.
- The CSS and HTML are compressed into strict "Safe-Mode" single-line strings.
- This repository contains only the compiled and obfuscated deployment files, fully optimized for GitHub Pages.

---

## 👨‍💻 About the Developer
**ClayScripts** focuses on creating premium, highly optimized, and aesthetically modern resources. This portfolio is designed to showcase my capabilities in bridging complex backend game logic with highly polished frontend user interfaces.

*© 2025 ClayScripts. All rights reserved.*
