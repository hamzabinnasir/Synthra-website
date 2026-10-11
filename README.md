# Synthra website

Static site (plain HTML + CSS, no build step, works with JavaScript disabled).

## Before publishing: replace every placeholder
Use VS Code **Find in Files** (Ctrl+Shift+H) across `synthra-website/`:

| Placeholder | Replace with |
|---|---|
| `{{LEGAL_NAME}}` | Legal business name, exactly as on your Business Verification documents |
| `{{ADDRESS}}` | Registered address, exactly as on those documents |
| `{{EMAIL}}` | Email on your own domain (not Gmail) |
| `{{DOMAIN}}` | `https://yourdomain` (no trailing slash) |
| `{{TEST_PAGE_URL}}` | Facebook Page / m.me link used for review testing |
| `{{EFFECTIVE_DATE}}` | Policy date |
| `{{AI_PROVIDERS}}` | Providers your backend really uses (check `fbbot/backend`, e.g. Groq, Google) |
| `{{AI_TRAINING_STATEMENT}}` | A true statement, e.g. "We do not use your data to train AI models." |
| `{{HOSTING_PROVIDER}}` | Where the backend runs |

Search for `{{` afterwards: there must be zero matches.

## Deploy
Cloudflare Pages, Netlify or Vercel: point at this folder, no build command, publish directory `.`. `_headers` (Netlify/Cloudflare) sets security headers. Connect your own domain over HTTPS.

## Meta App Dashboard values
Privacy Policy URL `/privacy.html` · Terms `/terms.html` · User data deletion URL `/data-deletion.html` (or your callback endpoint) · App icon: export `assets/logo.svg` as 1024x1024 PNG.

## Known gaps
- Data-deletion callback endpoint (`POST` with Meta `signed_request`) is not yet in the FastAPI backend; `/data-deletion.html` describes it.
- Add your own logo files to `assets/` if you want the full brand artwork. Do not use the flyer with its third-party logos and photo.
