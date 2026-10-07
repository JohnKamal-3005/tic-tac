# Antigravity Agent & Project Rules

Welcome to the **AG** workspace. This repository hosts interactive web applications and experiments, featuring the standalone **NEXUS Tic-Tac-Toe PRO** futuristic strategy arena and the **Squealing Solstice** Astro project.

All AI coding assistants (Antigravity, Gemini, Claude, etc.) operating in this workspace must adhere to the guidelines below.

---

## 1. Workspace Architecture & Directory Layout

- **`/` (Workspace Root)**:
  - `index.html`: Flagship standalone cyber-strategy Tic-Tac-Toe game engine with zero external runtime dependencies, HTML5 Canvas particle systems, Web Audio synthesis, Minimax AI, and responsive CSS design tokens.
  - `logo.jpg`: Project branding asset.
  - `AGENTS.md` / `GEMINI.md`: AI agent operational rules and standards.
  - `.agents/rules/`: Granular Antigravity rules and domain guides.
- **`squealing-solstice/`**:
  - Astro framework web application (TypeScript, Tailwind, Astro content collections).
- **`tic-tac/`**:
  - Dedicated Git repository subproject.

---

## 2. General Engineering Principles

1. **Preserve Documentation & Code Integrity**:
   - Maintain existing comments, docstrings, and structure unless explicitly tasked to refactor.
   - Do not remove existing features or themes when introducing new functionality.
2. **Zero-Broken-State Policy**:
   - Test changes locally before marking tasks complete.
   - For standalone web pages (`index.html`), verify syntax and browser compatibility.
   - For Astro (`squealing-solstice`), verify TypeScript checks and build commands pass.
3. **No External Dependencies for Standalone Root Apps**:
   - Keep `index.html` self-contained (pure vanilla HTML5, CSS3, and JavaScript).
   - Use standard Web APIs (`AudioContext`, Canvas 2D, `localStorage`, `requestAnimationFrame`).

---

## 3. UI/UX & Aesthetic Standards

1. **Futuristic, Premium Aesthetics**:
   - All interfaces must feel polished, modern, and engaging.
   - Utilize themeable CSS custom properties (variables) for all color tokens, glows, and surface backgrounds.
   - Incorporate subtle glassmorphism (`backdrop-filter: blur(...)`), neon accents, and smooth cubic-bezier transitions (`--ease-spring`, `--ease-smooth`).
2. **Responsive & Accessible**:
   - Ensure mobile-first or highly responsive layouts supporting desktop, tablet, and mobile breakpoints.
   - Provide proper ARIA roles, descriptive `aria-label` attributes, and keyboard shortcuts.
   - High-contrast visual cues for active turns, winning lines, and expiring marks.
3. **Sound & Motion**:
   - Any audio should use synthesized Web Audio API oscillators with smooth gain ramps to avoid clipping.
   - Provide a global mute toggle (`M`) and store sound preferences in `localStorage`.

---

## 4. Game Development Rules (`index.html`)

1. **Game State Management**:
   - Game state must be centralized in the `state` object (grid size, win targets, scores, history, board array).
   - Dynamic win conditions:
     - 3×3 Grid: 3-in-a-row win target.
     - 4×4 & 5×5 Grids: 4-in-a-row win target.
2. **Modifier Protocols**:
   - **Infinity Mode**: Strict queue constraint. Only `winTarget` marks per player allowed simultaneously. Oldest mark flashes (`expiring-soon`) and dissolves on the subsequent move.
   - **Blitz Mode**: Strict per-turn timer (e.g. 8s). Countdown runs smoothly and applies a fallback random move if expired.
3. **AI Protocols**:
   - **Impossible**: Unbeatable Minimax evaluation with alpha-beta pruning / depth bounds for larger matrices.
   - **Medium**: Tactical win-and-block heuristics with strategic center/corner preferences.
   - **Easy**: Casual randomized decision-making.

---

## 5. Astro Project Rules (`squealing-solstice`)

1. **Dev Server**:
   - Start background servers using:
     ```bash
     astro dev --background
     ```
   - Control via `astro dev stop`, `astro dev status`, and `astro dev logs`.
2. **Components & Styling**:
   - Prefer semantic Astro components (`.astro`) over heavy client-side framework scripts when static rendering is sufficient.
   - Follow standard Tailwind CSS utility patterns defined in the project.

---

## 6. Git & Commit Guidelines

- Write concise, imperative commit messages (e.g., `feat: enhance in-game rules modal with interactive tabs`).
- Keep diffs focused; avoid unnecessary whitespace or bulk reformatting.
