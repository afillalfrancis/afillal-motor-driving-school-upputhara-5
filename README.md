# Afillal Motor Driving School, Upputhara

Website with **Clint**, the waving instructor. Click him to chat in **English or Malayalam**. Clint is powered by Google Gemini.

```
public/index.html   the website (add your classes.html here too)
api/chat.js         Clint's AI (Vercel serverless function calling Gemini)
vercel.json         tells Vercel to serve /public
```

## 1. Put it on GitHub
1. Create a new repository on github.com (Private is fine).
2. Click **Add file > Upload files** and drag in the *contents* of this folder (public, api, and the other files, not a zip).
3. Click **Commit changes**.

## 2. Get a free Gemini key
Go to https://aistudio.google.com/apikey and create a key. Set a spending or quota limit there so nobody can run up costs.

## 3. Deploy on Vercel (free plan works)
1. Go to https://vercel.com, sign in with GitHub, click **Add New > Project**, and import your repository.
2. Before deploying, open **Environment Variables** and add `GEMINI_API_KEY` with your key.
3. Click **Deploy**. Your site and Clint are live at your `.vercel.app` address. Every future GitHub commit redeploys automatically.

Do not put the key in `index.html` or commit it to GitHub.

## Using GitHub Pages for the page instead
GitHub Pages cannot run `api/chat.js`, so deploy to Vercel as above and open `public/index.html`, change `var CHAT_API="/api/chat"` to your full Vercel address (for example `https://your-app.vercel.app/api/chat`), and add `ALLOWED_ORIGIN=https://your-username.github.io` in Vercel.

## Test on your computer
`npx vercel dev` (put `GEMINI_API_KEY=...` in `.env.local` first).

## Notes
- If the AI is unreachable or out of quota, Clint switches to built-in answers in both languages, so the chat never breaks.
- To change what Clint knows or how he talks, edit the `SYSTEM` text in `api/chat.js`.
