# Felice.ai Frontend — Backend Connected

## Included
- Mobile-responsive workspace UI
- Supabase email/password sign-in and sign-up
- Settings for backend URL, Supabase URL and Supabase Publishable Key
- Authenticated Gemini text generation using the exact backend contract: `POST /api/ai/text` with `{ "prompt": "..." }`
- My Projects using backend `GET`, `POST`, `PATCH`-compatible schema and `DELETE` routes; current UI supports list, create, open and delete
- Editable results, copy and TXT download
- Cookie preference and local settings

## Deploy on GitHub Pages
1. Extract this ZIP.
2. Put your own `logo.png` in this same folder (optional).
3. Upload `index.html`, `style.css`, `app.js`, and `README.md` to your GitHub Pages repository root.
4. Open your published site → Settings.
5. Backend URL: `https://felice-ai-backend.onrender.com`
6. Supabase URL: `https://ctqexjixhclnorychbzp.supabase.co`
7. Paste the Supabase **Publishable Key** from Supabase Dashboard → Project Settings → API Keys.
8. Tap **Save settings & connect**, then sign in/create account.

## Backend configuration required
Render environment variables must include:
- `SUPABASE_URL`
- `SUPABASE_PUBLISHABLE_KEY`
- `GEMINI_API_KEY`
- optional `GEMINI_MODEL` (defaults to `gemini-2.5-flash`)
- `FRONTEND_ORIGIN` must include the exact deployed origin, e.g. `https://USERNAME.github.io` (origin only, no `/Aone` path)

Run `supabase/schema.sql` from the backend ZIP in Supabase SQL Editor to create the projects table and RLS policies.

## Honest feature status
The supplied backend implements authenticated Gemini **text generation** and user-scoped project CRUD. It does not implement image generation, video generation, text-to-speech, media uploads/transcoding, or a video editing worker. Those UI sections can prepare a creative brief through the text endpoint, but they do not generate/edit actual media yet. Gemini key stays on Render and is never placed in frontend settings.

## Security
Only use the Supabase Publishable Key in the browser. Never paste a Supabase Secret/Service Role key or Gemini API key into frontend settings or commit them to GitHub.
