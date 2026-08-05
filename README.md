# Declarative Password Meter

An evaluation UI that tracks credential strength directly inside the browser engine using HTML field patterns and modern layout pseudo-selectors.

## Overview & Value Proposition

Form validation often ships with heavy JavaScript bundles just to check input requirements. This codebase handles password criteria evaluation using built-in HTML regex patterns combined with `:has()`, `:user-invalid`, and `:valid` target conditions. 

By moving state detection into standard layout evaluation rules, the interface responds immediately to user interaction without binding event listeners or processing input strings in script memory.

## How It Works

1. **HTML5 Regex Enforcement:** The input element defines complexity constraints using standard attributes: minimum length of 8 characters along with upper, lower, numeric, and special character requirements.
2. **State Bubble-Up:** Parent containers watch child input state transitions through the `:has()` relational selector.
3. **Visual Meter Updates:** As fields match `:placeholder-shown`, `:user-invalid`, or `:valid`, CSS variable rules adjust gauge bar width percentages and color fills dynamically.

## Key Features

* **Zero Script Execution:** Operates strictly through engine parsing algorithms.
* **Native State Handling:** Uses `:user-invalid` so error styles wait until the user finishes typing or switches fields.
* **Instant Dynamic Feedback:** Updates bar length and label content using CSS pseudo-elements (`::before`).

## Tech Stack Breakdown

* **HTML5:** Semantic markup utilizing structural attributes (`pattern`, `minlength`, `placeholder`).
* **CSS3:** Built with Flexbox, pseudo-class state chaining (`:has()`), and pseudo-element generation.

## Prerequisites & Web-Based Quick Start

You don't need local node setups or terminal commands to run or inspect this project.

### Running via GitHub Codespaces

1. Click the **Code** button at the top right of this repository.
2. Select the **Codespaces** tab and click **Create codespace on main**.
3. Open `index.html` in the browser preview extension or launch a web server extension inside the browser editor.

### Local File Option

1. Download `index.html` and `style.css`.
2. Double-click `index.html` to open it in any updated browser.

## Repository Structure

```text
├── .github/
│   └── workflows/
│       └── validation.yml   # W3C structural and syntax validation pipeline
├── index.html               # Signup card markup containing input regex constraints[cite: 1]
├── style.css                # Style rules, state transitions, and meter mechanics
├── .gitignore               # System file ignores
└── LICENSE                  # MIT License
```

## Roadmap

[ ] Add dynamic feedback criteria checklist (e.g., individual indicators for uppercase, digits, symbols).

[ ] Incorporate toggle visibility controls for password fields.

[ ] Add dark theme styling overrides via media queries.
