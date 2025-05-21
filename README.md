# React + TypeScript + Vite
# Paradox-XX
Paradox-XX is a modern, browser-based strategy game developed using React and TypeScript, designed for a seamless and responsive web experience. The game features three default 3x3 boards and supports custom board sizes ranging from 2x2 to 5x5, allowing for highly dynamic gameplay. It offers two game modes: Player vs Player (PvP) with customizable player names and Player vs Computer (PvC) featuring five levels of AI difficulty. The AI is powered by the Minimax algorithm with alpha-beta pruning, enabling strategic decision-making up to a depth of 4 moves. An in-game economy enhances the experience, letting players use 100 coins to undo a move or 200 coins to skip a turn. Coins and XP are distributed using the balanced formula n × s × d × r, where 1 ≤ r ≤ 10. Player progress is securely stored in Firebase using Google Sign-In, ensuring real-time cloud synchronization. The game also features sound effects for moves and victories, blurred visuals for completed boards, and optimized performance across all board sizes and game modes. The tech stack includes JavaScript, React, TypeScript, and Firebase.

## Features
Dynamic board dimensions (2x2 to 5x5)

PvP with custom player names

PvC with 5 AI difficulty levels

Minimax with alpha-beta pruning (depth 4)

In-game currency (Undo/Skip)

Sound effects and board animations

Google Sign-In with Firebase real-time sync

Responsive design for all screen sizes

## Tech Stack
React

TypeScript

JavaScript

Firebase (Auth, Firestore)

CSS Modules / Styled Components (as applicable)

## Installation
bash
Copy
Edit
git clone https://github.com/your-username/paradox-xx.git
cd paradox-xx
npm install
npm start
## Usage
Visit http://localhost:3000 (or deployed URL).

Sign in with Google to save progress.

Choose game mode: PvP or PvC.

Start playing with custom or default board dimensions.

## Game Rules
Players take turns placing their marks.

Game ends when all boards are dead or won.

Win conditions depend on board dimension (e.g., 3 in a row for 3x3).

## In-Game Economy
Undo Move – Costs 100 coins

Skip Turn – Costs 200 coins

XP/Coins Formula – n × s × d × r (1 ≤ r ≤ 10)

## AI Logic
Uses Minimax with alpha-beta pruning.

Analyzes up to 4-depth decisions for strategic play.

5 difficulty levels tweak AI aggressiveness.

## Firebase Integration
Google Sign-In for authentication.

Real-time Firestore DB sync for progress.

Secure data handling.

## Sound & UI Effects
Click and win sound effects.

Blurred visuals for completed (dead) boards.

Smooth, responsive transitions across all modes and screen sizes.

## Contributing
Contributions are welcome! Please fork the repo and submit a pull request.
Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```
