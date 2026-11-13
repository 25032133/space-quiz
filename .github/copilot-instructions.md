# Copilot instructions

## Application structure

- `space-exploration-quiz.html` contains the complete quiz: semantic HTML, inline CSS, and inline JavaScript. The browser runs it directly.
- The `questions` array is the source of quiz content. Each entry uses `question`, `answers`, zero-based `correct`, and `explanation`. `showQuestion` renders the current item, `selectAnswer` handles scoring and feedback, and the next-button handler advances to `showResults` at the end.
- Quiz state (`currentQuestion`, `score`, and `answered`) is kept in the page script. Use `questions.length` as the quiz length rather than duplicating the count.

## UI and behavior conventions

- Theme colors are CSS custom properties declared in `:root` and overridden in `[data-theme="dark"]`. `setTheme` applies the theme to the document element; the preference is stored as `orbit-theme`, with the system color preference as the initial fallback. Add theme-aware colors to both token sets.
- JavaScript queries elements by their HTML IDs. Keep those IDs in sync with the script when changing the page structure.
- Answer choices and actions are native buttons. Preserve the progress bar semantics, live announcements for score and feedback, and `aria-hidden` on decorative graphics. Keep visible keyboard focus and the reduced-motion styles when changing interactions or animations.
- The centered layout adapts at the 420px breakpoint; keep the quiz usable at narrow viewport widths.
