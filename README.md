# Riccardo Civiero — Portfolio

Personal portfolio website — Cybersecurity & Software Developer.

🌐 **Live site:** [https://spidercivi.github.io](https://spidercivi.github.io)

## Stack

- HTML + React 18 (CDN, no build step)
- Babel Standalone (in-browser JSX transpilation)
- Canvas 2D — animated cyber globe with live threat arcs
- EmailJS v4 — contact form email delivery
- Cloudflare Turnstile — free bot/spam protection on the contact form
- JetBrains Mono + Space Grotesk

## Features

- Multilingual UI — EN / IT / ES / FR / DE
- Dark theme with accent colour picker
- Animated sections with scroll-reveal
- Contact form with:
  - Real-time email validation + disposable-email blocklist
  - Cloudflare Turnstile CAPTCHA (anti-bot)
  - Client-side rate limiting (max 3 messages / hour)
  - XSS sanitisation on all inputs

## Contact form setup

### EmailJS
1. Create a service and template at [emailjs.com](https://www.emailjs.com)
2. The template can use any of these variables (all are sent): `from_name`, `user_name`, `name`, `from_email`, `user_email`, `email`, `message`, `reply_to`, `subject`, `to_name`
3. Replace the public key in `index.html` → `emailjs.init({ publicKey: '...' })`

### Cloudflare Turnstile (free)
1. Go to [dash.cloudflare.com](https://dash.cloudflare.com) → **Turnstile** (account sidebar, not inside a site)
2. Create a widget for `spidercivi.github.io`
3. Copy the **Site Key** and replace `TURNSTILE_SITE_KEY` in `index.html`

> Note: Cloudflare DNS proxy does not apply to `*.github.io` subdomains (owned by GitHub). Turnstile works independently and does not require DNS proxy.
