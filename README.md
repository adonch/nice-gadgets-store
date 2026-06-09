# Nice Gadgets Store

A small React + TypeScript single page app (SPA) showcasing phones, tablets and accessories with cart and favorites support.

## Overview

- Modern frontend demo built with Vite, React 18 and TypeScript.
- Uses CSS Modules + SCSS for styling, local JSON files in `public/api` as a simple data source, and local images under `public/img`/`img`.

## Tech Stack

- React 18 + TypeScript
- React Router v6
- Redux (Redux Toolkit)
- CSS Modules + SCSS
- Vite (dev server / build)

## Key Features

- Home page with hero slider and product carousels
- Category pages: phones, tablets, accessories (sorting, pagination, URL-persisted params)
- Product detail pages with gallery, configurator and specs
- Cart with quantity controls and localStorage persistence
- Favorites (toggle hearts) persisted in localStorage
- Light / Dark theme toggle and responsive layout

## Repo layout

Top-level important folders:

```
public/
	├─ api/        # JSON product feeds used by the app
	└─ img/        # product and icon images

src/
	├─ app/        # layout, providers, router
	├─ features/   # app features (cart, favorites, product, home)
	├─ pages/      # top-level pages
	├─ shared/     # shared components, services
	└─ styles/     # global styles and variables
```

Components generally follow the pattern: `ComponentName/` with `index.ts`, `ComponentName.tsx`, and `ComponentName.module.scss`.

## Getting started (development)

Prerequisites:

- Node.js 18+ (or current LTS)
- npm (or yarn)

Install dependencies and start dev server:

```bash
npm install
npm start
```

By default Vite serves on `http://localhost:5173`. Open the URL shown by the dev server.

## Available scripts

- `npm start` — start Vite dev server
- `npm run build` — production build
- `npm run lint` — run ESLint

## Local API / Data

This project reads static JSON files from `public/api` (for example `public/api/products.json`, `phones.json`, etc.). In development the Vite dev server serves those files at `/api/<file>.json` out of the `public` folder, so components can fetch them with a relative URL such as `/api/phones.json`.

If you need to mock additional endpoints, add JSON files to `public/api`.

## Development notes

- Image assets are stored under `public/img` and `img/` in the workspace — keep filenames stable when updating components.
- Application state: `store/store.ts` and slices in `store/slices/` (Redux Toolkit).
- Theme handling uses `src/app/providers/ThemeContext.tsx` and CSS variables in `src/styles`.
- Routing lives in `src/routes/AppRouter.tsx` and route paths in `src/routes/RoutePaths.ts`.

## Testing & Linting

No test runner is included by default. ESLint can be run with:

```bash
npm run lint
```

