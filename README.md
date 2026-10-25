# Node.js Event Loop Playground

An interactive, browser-based simulator to understand how the **Node.js Event Loop** works through step-by-step execution.

The playground helps developers visualize the Call Stack, `process.nextTick()` queue, Promise microtask queue, timers, and `setImmediate()` callbacks.

## Features

- **Interactive JavaScript Editor:** Write and execute supported Node.js snippets directly in the browser.
- **Line Numbers:** Easily identify the source line of every statement.
- **Call Stack Visualization:** See which callback is currently executing.
- **Queue Visualization:** Track callbacks in different queues.
- **Unique Callback Labels:** Identify each `nextTick` and Promise callback using labels such as:
  - `N1(line 23)` – First `process.nextTick()` callback.
  - `N2(line 45)` – Second `process.nextTick()` callback.
  - `P1(line 44)` – First Promise callback.
- **Step-by-Step Execution:** Move forward or backward through execution.
- **Play and Pause:** Watch the execution flow automatically.
- **Console Output:** Follow the output as each callback executes.

## Screenshots

Add screenshots of the playground here to demonstrate the editor, queues, and execution steps.

## Getting Started

No installation, dependencies, or build process are required.

1. Download or clone this repository.
2. Open `Node_Event_Loop_Playground_Harish.html` in your browser.
3. Write or paste your JavaScript snippet in the editor.
4. Click **Run / Parse**.
5. Use Next, Previous, Play, and Pause to explore the execution flow.

## Supported JavaScript Syntax

The simulator supports a limited subset of JavaScript:

### 1. Console Output

```javascript
console.log("Hello Node.js");
console.log("Event Loop");
```

### 2. process.nextTick()

```javascript
process.nextTick(() => {
  console.log("Next Tick Callback");
});
```

### 3. Promise Microtasks

```javascript
Promise.resolve().then(() => {
  console.log("Promise Callback");
});
```

### 4. setTimeout()

```javascript
setTimeout(() => {
  console.log("Timer Callback");
}, 0);
```

### 5. setImmediate()

```javascript
setImmediate(() => {
  console.log("Immediate Callback");
});
```

Nested callbacks are supported within these structures.

## Understanding Callback Labels

The simulator assigns unique labels to `nextTick` and Promise callbacks.

| Label | Meaning |
|---|---|
| N1(line 5) | First nextTick callback scheduled from line 5 |
| N2(line 10) | Second nextTick callback scheduled from line 10 |
| P1(line 7) | First Promise callback scheduled from line 7 |
| P2(line 12) | Second Promise callback scheduled from line 12 |

Numbering is independent for `nextTick` and Promise callbacks.

The line number refers to the source line where the callback is scheduled, making it easier to trace callbacks back to the original code.

## Execution Model

The simulator models CommonJS-style top-level scheduling.

The simplified execution flow is:

1. Execute synchronous JavaScript statements.
2. Drain the `process.nextTick()` queue.
3. Drain the Promise microtask queue.
4. Process scheduled timer and immediate callbacks.
5. Perform microtask checkpoints after scheduled callbacks.

The simulator also demonstrates how callbacks scheduled inside other callbacks are added to their respective queues.

## Important Limitations

This is an educational simulator, not a complete JavaScript engine or Node.js runtime.

The following are not supported:

- Variables and expressions.
- Loops and conditional statements.
- `async/await`.
- File system and network I/O.
- Imports and exports.
- Arbitrary JavaScript syntax.

**Timer ordering:** When both top-level `setTimeout(0)` and `setImmediate()` are scheduled, the simulator uses a deterministic timers-first convention. Actual Node.js execution order can vary depending on the execution context and runtime conditions.

## Tech Stack

- HTML5
- CSS3
- Vanilla JavaScript

No external libraries or frameworks are required.

## Author

**Harish**  
Software Engineer | Backend Developer

- Phone: +91 7011206655
- Email: [harishk2711992@gmail.com](mailto:harishk2711992@gmail.com)
- GitHub: [Harish-kumar99](https://github.com/Harish-kumar99)
- Medium: [@harishk271199](https://medium.com/@harishk271199)

---

© 2026 Harish. All rights reserved.

*Built as a learning tool to make Node.js event loop execution easier to understand and visualize.*
