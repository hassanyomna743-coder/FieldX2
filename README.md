# FieldX
npm install && npm run dev  (Vercel: Framework Vite, build `npm run build`, output `dist`)
public/: earth.mp4 (home hero only), globe.mp4 (tool search background, dissolves into zoom.mp4 when a place is picked), zoom.mp4 (final satellite zoom). Glitch runs only on language/dialect change.
Earthdata (SMAP/ECOSTRESS): needs a server function + EARTHDATA_TOKEN env var (next step).

## AI advisor (chat on every page)
`api/chat.js` streams answers from Google Gemini. In Vercel → Settings → Environment Variables add `GEMINI_API_KEY` (from aistudio.google.com/apikey) and optionally `GEMINI_MODEL` (default `gemini-3.5-flash`), then redeploy.
The Tool publishes the selected land (place or drawn polygon, crops, soil inputs, NASA/ERA5/SRTM data, computed plans) to `src/ctx.js`; `src/Chat.jsx` sends it with every question. If the land was not analyzed yet, the chat runs the analysis first.
