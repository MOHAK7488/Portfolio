# Mohak bot API (Cloudflare Worker)

Gives the public site real AI answers. The page calls this worker, the worker calls the Anthropic API, and the API key never reaches the browser.

## Deploy (about 10 minutes, free tier)

1. Create an API key at console.anthropic.com (Settings, API keys).
2. Sign up at cloudflare.com, open Workers & Pages, choose Create, then Create Worker, and name it `mohak-bot`.
3. Choose Edit code, paste the contents of `worker.js`, and deploy.
4. In the worker, open Settings, Variables and Secrets, add a secret named `ANTHROPIC_API_KEY` with your key, and deploy again.
5. Copy the worker URL (looks like `https://mohak-bot.<name>.workers.dev`).
6. Send that URL to Claude, or set `var BOT_API_URL = '...'` in `index.html` yourself.

The worker only accepts requests from https://mohak7488.github.io. Edit `ALLOWED_ORIGINS` in `worker.js` if you use a custom domain.
