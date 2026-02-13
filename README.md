# ❌⭕ React Tic-Tac-Toe

> **A classic game built to master the fundamentals of React.js.**

<img width="388" height="428" alt="image" src="https://github.com/user-attachments/assets/3e2540ae-74c7-45ed-9da1-b6fbe22f7d6b" />

## 👋 About The Project
This isn't just a game of Tic-Tac-Toe; it's my first step into the React ecosystem. I built this project to understand the core philosophy of React: thinking in components, managing state, and handling user interaction without touching the DOM directly.

It features a functional 3x3 grid where two players can compete, with automatic win detection and turn-based logic.

## 🧠 What I Learned (Key Concepts)
While building this, I focused on these specific React patterns:

### 1. Component Architecture
I broke the UI down into small, reusable pieces.
* **`Square`**: A dumb component that simply displays a value (`X`, `O`, or null) and listens for clicks.
* **`Board`**: A smart component that holds the state of the game and renders the 9 squares.

### 2. State Management (`useState`)
I learned how to use the `useState` hook to keep track of data that changes over time:
* Tracking which squares are filled.
* Tracking whose turn it is (`xIsNext`).

### 3. Lifting State Up
Initially, I thought each Square should track its own state. However, I learned that to determine a winner, the **Board** needs to know the state of all squares. I "lifted" the state up from the children (`Square`) to the parent (`Board`) so the parent could control the logic.

### 4. Immutability
Instead of changing the array of squares directly, I learned to create a copy using `.slice()`:
```javascript
const nextSquares = squares.slice(); // Create a copy
nextSquares[i] = 'X';                // Modify the copy
setSquares(nextSquares);             // Replace the old state
