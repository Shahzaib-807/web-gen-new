# WebGen AI — React + Vite + OpenRouter

A complete AI website generator. Users enter a prompt, the backend asks OpenRouter for a standalone HTML website, and the app provides a live preview, source view, copy, HTML download, and ZIP download.

## 1. Install

```bash
npm install
```

## 2. Configure OpenRouter

Copy `.env.example` to `.env` and put your own OpenRouter key in `OPENROUTER_API_KEY`.

**Never commit `.env` or put the key in React/Vite client code.**

Optional model override:

```env
OPENROUTER_MODEL=openrouter/free
```

## 3. Run

```bash
npm run dev
```

Open http://localhost:5173

The API runs on http://localhost:3000 and Vite proxies `/api/*` to it.

## 4. Production build

```bash
npm run build
```

The generated website itself is a standalone `index.html`, so the downloaded ZIP can be opened directly in a browser.

## Troubleshooting

- `404` from `/api/generate`: make sure `npm run dev` is running both the Vite client and Node server. Check http://localhost:3000/health.
- `OPENROUTER_API_KEY is missing`: create `.env` from `.env.example`, add your key, then restart `npm run dev`.
- If a free model is temporarily unavailable, try again or set `OPENROUTER_MODEL` to another currently available OpenRouter model.
