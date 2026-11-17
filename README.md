# Wayfarer — free, self-hosted trip planner

One static file (`index.html`). No server, no build step, no Claude tokens.

## Host it (all free)
**GitHub Pages:** create a repo → upload `index.html` → *Settings → Pages → Deploy from branch → main / root*. Your site appears at `https://<you>.github.io/<repo>/`.
Other options: Cloudflare Pages, GitLab Pages, Vercel, Surge, or any static host. You can also just open the file locally.

## What it uses (no keys needed unless noted)
| Need | Service |
|---|---|
| Map tiles | OpenStreetMap + Leaflet |
| Search / click-to-name | Nominatim |
| Road routes & drive times | OSRM public demo server |
| Real restaurants, sights, stays | Overpass API (OpenStreetMap data) |
| Currency rates | open.er-api.com (falls back to built-in rates) |
| AI curation | Pick in **⚙ Settings** (see below) |

## Free AI options (⚙ Settings)
- **Pollinations** – no key. Default. Availability can change.
- **Groq**, **Google Gemini**, **OpenRouter (free models)** – create a free API key, paste it in Settings.
- **Local Ollama** – run `OLLAMA_ORIGINS=* ollama serve`, choose “Local Ollama”.
- **No AI** – built-in planner using OpenStreetMap data only. If an AI call fails, the app falls back to this automatically.

Keys are stored in your browser’s localStorage and are only sent to the provider you choose.

## Developer mode
Tick **Developer mode** in Settings for: request/response log, AI connection test, and a live JSON editor for the plan.

## Sharing & editing
The whole plan is compressed into the page URL (`#p=…`), so there is no database. Click **Share**, send the link, and the recipient can open and edit it. Every edit refreshes the address bar; copy the new link to share changes back.
True live co-editing needs a backend (e.g. Firebase/Supabase) and isn’t included.

## Please be kind to the free services
Nominatim and Overpass are community-run with usage limits; the app spaces its requests out. For heavy use, host your own instances or swap the endpoints in the code.
