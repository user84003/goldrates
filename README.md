# Gold rates: Chandukaka vs PNG

A static page (GitHub Pages) that compares today's gold rates per gram from
Chandukaka Saraf and PNG Jewellers. A GitHub Action scrapes both sites every
hour and commits the result to `rates.json`.

## Files
- `index.html` – the page
- `rates.json` – latest rates (rewritten by the Action)
- `fetch_rates.py` – scraper run by the Action
- `.github/workflows/rates.yml` – hourly schedule (09:35–21:35 IST)
- `worker.js` – optional Cloudflare Worker alternative (live fetch on every tap)

## Setup
1. Push all files to the repo root (keep the `.github` folder).
2. Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.
3. Settings → Actions → General → Workflow permissions → Read and write.
4. Actions tab → "Update gold rates" → Run workflow (first run).
5. Site: `https://<user>.github.io/<repo>/`

## Notes
- 14K is not listed by Chandukaka, so it is estimated as 24K × 0.63.
- If a site changes its layout, the Action keeps the old rates and shows an error on the page.
