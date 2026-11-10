# Lecture Notes Helper

Paste a lecture text, get short notes, key terms and a 5-question self-check.

## Files

- `index.html` — the whole interface (HTML, CSS, JavaScript)
- `netlify/functions/generate.js` — small server function; it holds the AI key and calls the Gemini API
- `netlify.toml` — tells Netlify where the function lives

## Deploy (free): GitHub + Netlify

1. Get a free key in Google AI Studio (aistudio.google.com → "Get API key").
2. Create a GitHub repository and upload these files, keeping the folder structure. Never put the key in any file.
3. In Netlify: Add new site → Import an existing project → pick the repository. Leave the build settings as they are.
4. Before the first deploy (or afterwards, then redeploy): Site configuration → Environment variables → add `GEMINI_API_KEY` with your key.
5. Optional: `GEMINI_MODEL` if you want a different model than the default `gemini-3.8-flash`.
6. Site configuration → Change site name → pick your own address, e.g. `your-name.netlify.app`.

## Run locally

    npm install -g netlify-cli
    GEMINI_API_KEY=your_key netlify dev

Then open the address it prints.

## Notes

- On Google's free tier, inputs may be used to improve their models, so do not paste private material.
- If you get "Too many requests", you hit the free-tier limit; wait a minute.
