# Personal Website

A minimal static personal website — single `index.html` file with no build step or dependencies.

## Stack
- Plain HTML, CSS, JavaScript (no framework)
- Self-contained: everything is in `index.html`

## Dev Server
```bash
# Node (port 3000) — preferred
npx serve . --listen 3000

# Python fallback (port 8000)
python -m http.server 8000
```
Use `preview_start` with `"serve (Node)"` or `"http.server (Python)"` from `.claude/launch.json`.

> **Note:** On Windows, `npx` must be invoked via `cmd /c` — this is already handled in `launch.json`.

## Customization
Edit these sections in `index.html`:

| What | Where |
|------|-------|
| Avatar | Replace the `AJ` initials div with `<img src="your-photo.jpg">` |
| Name | `<h1 class="name">` |
| Role | `<p class="role">` |
| Bio | `<p class="bio">` |
| Social links | `<div class="links">` — update `href` values |
| Contact form backend | Replace the `fetch` comment with a Formspree/EmailJS call |

## Contact Form
The form is frontend-only. To make it functional, sign up at [Formspree](https://formspree.io), get a form ID, and replace the comment in the `submit` handler:
```js
fetch('https://formspree.io/f/YOUR_ID', { method: 'POST', body: new FormData(form) })
```
