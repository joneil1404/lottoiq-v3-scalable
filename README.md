# LottoIQ Version 3 — Scalable Foundation

LottoIQ is now a modular React + TypeScript application rather than a single HTML file.

## Architecture

- `src/config/games.ts` — lottery definitions and source-specific parsers
- `src/services/drawService.ts` — data retrieval
- `src/analytics/engine.ts` — reusable game-agnostic calculations
- `src/components` — reusable visual and interaction components
- `src/App.tsx` — application shell and navigation
- `.github/workflows/deploy.yml` — automatic GitHub Pages deployment

## Current game

- Mega Millions

## Adding a game

Add another `LotteryGame` object to `src/config/games.ts`, including:

- primary number range and count
- bonus range
- official data source
- parser that maps each record to the shared `Draw` type

The existing heat map, momentum, matrix, statistics, and ticket components then work from the shared configuration.

## Local setup

1. Install Node.js 20 or later.
2. Run:

```bash
npm install
npm run dev
```

## Deploy to GitHub Pages

This repository includes an automatic workflow.

1. Upload all project files to a GitHub repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, select **GitHub Actions**.
4. Push or commit to the `main` branch.
5. Open the **Actions** tab and wait for the deployment to complete.
6. Your existing Pages address will display the new React application.

## Important migration note

This is a full project rather than a replacement `index.html`. Upload the complete project structure, including the hidden `.github` folder.

## Disclaimer

LottoIQ describes historical drawing data. It does not predict independent future drawings.
