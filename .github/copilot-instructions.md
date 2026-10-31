# Copilot Instructions

## Architecture & Project Structure

This project is a zero-dependency, single-file web application contained entirely within `index.html` (inline CSS and vanilla JavaScript). It runs directly via `file://` URLs without a build step, bundler, or local server.

- **Bilingual State (`I18N`)**: All UI strings, telemetry headers, rank titles/subtitles, and the 10 quiz questions (including options and explanations) are stored in the `I18N` dictionary under `en` and `ko` keys (`currentLang` defaults to `"ko"`).
- **Non-Destructive Language Switching**: Switching languages mid-question calls `renderQuestion(true)`, which re-renders localized text and re-applies answered state (`applyAnsweredUI(selectedOptionIndex)`) without resetting `score`, `currentIndex`, or `answered`.
- **View Lifecycle**: The app toggles visibility between `#quiz-view` and `#results-view` using the `.hidden` class (`display: none !important`).

## Verification & Smoke Testing

There is no package manager or test runner. Verify changes in the integrated browser canvas (`file:///Users/ivy/Documents/github_test/index.html`):

- When reloading after edits, append or increment a query string (e.g., `?v=2`) if the canvas caches the previous `file://` document.
- Use `evaluate_javascript` on the browser canvas to run automated smoke checks covering keyboard navigation (`ArrowUp`/`ArrowDown`, `A`–`D`, `1`–`4`, `Enter`/`Space`), `.correct` (`pulseGreen`) and `.wrong` (`shakeRed`) feedback states, live score increments, and results view transitions.

## Key Conventions

- **Bilingual Parity**: Every new question, UI label, or result tier must be added to both `I18N.en` and `I18N.ko` with matching `answer` indices (`0`–`3`).
- **Mission-Control HUD Theme**: Styling relies on CSS custom properties in `:root` with automatic `@media (prefers-color-scheme: dark)` overrides. Preserve the HUD brackets (`.container::before`/`.container::after`), 24px background grid (`--card-surface-grid`), telemetry top bar (`.telemetry-strip`), and monospace readouts (`--mono`) across both light and dark modes.
- **Keyboard & Focus Management**: Maintain automatic focus transitions—first option on new question render, `#next-btn` after answering, and `#restart-btn` on the results screen.
