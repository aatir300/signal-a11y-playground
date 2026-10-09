# Signal: an accessibility playground

A small, single-file web app that teaches the basics of web accessibility (WCAG 2.1 AA) through hands-on practice. No frameworks, no build step, no dependencies.

## What it teaches

Websites should work for people who use only a keyboard, use a screen reader, have low vision, or are color-blind. Signal has three short labs:

| Lab | What you do | What you learn |
| --- | --- | --- |
| **Contrast lab** | Pick a text color and a background color | How WCAG measures contrast, and what 4.5:1 and 3:1 mean |
| **Keyboard playground** | Use an accordion and a dialog with only Tab, Enter, Space and Esc | Focus order, focus visibility, and why real buttons matter |
| **Break and fix** | Compare a broken signup card with a fixed one | Six common mistakes, their WCAG criteria, and how to repair them |

## Run it

1. Download `index.html` (rename `signal-a11y-playground.html` if needed).
2. Open it in any modern browser.

That's it. To host it free, use **GitHub Pages**: Settings > Pages > deploy from the `main` branch.

> The page loads one optional Google Font (Bricolage Grotesque). If you are offline it falls back to the system font and everything still works.

## Accessibility features used in the app itself

- Skip link and a logical heading structure
- Native `<button>` and `<dialog>` elements instead of custom widgets
- `aria-expanded`, `aria-controls` and `aria-pressed` only where HTML cannot express the state
- `aria-live` and `role="status"` so screen readers announce updates
- Visible `:focus-visible` outlines on every control
- Results shown with text and icons, never color alone
- Light and dark themes with checked contrast, and `prefers-reduced-motion` support
- Touch targets at least 44px tall

## How the contrast checker works

Each color is converted to a relative luminance value using the WCAG formula. The ratio is then:

```
(lighter luminance + 0.05) / (darker luminance + 0.05)
```

Thresholds: **4.5:1** for normal text, **3:1** for large text and UI components, **7:1** for AAA normal text. The displayed ratio is rounded down so a failing value never appears to pass.

## Project structure

```
index.html   # HTML, CSS and JavaScript in one file, commented section by section
README.md
```

## Limitations

This tool teaches fundamentals and cannot replace testing with real assistive technology. Always check your work with a screen reader (NVDA, VoiceOver, TalkBack), keyboard-only navigation, browser zoom to 200%, and automated scanners such as axe DevTools, Lighthouse or WAVE. Automated tools find only part of all accessibility issues.

## Ideas to extend it

- Add a color-blindness simulator
- Add a form-validation lab with an error summary
- Add a text-spacing and reflow test
- Add an exportable audit checklist

## References

- [WCAG 2.1 overview](https://www.w3.org/TR/WCAG21/)
- [How to Meet WCAG (Quick Reference)](https://www.w3.org/WAI/WCAG21/quickref/)
- [ARIA Authoring Practices Guide](https://www.w3.org/WAI/ARIA/apg/)

## License

MIT. Use it, change it, and learn from it.
