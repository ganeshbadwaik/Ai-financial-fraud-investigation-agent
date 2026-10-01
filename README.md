# FRAUD-X

FRAUD-X is a React 19 and TypeScript frontend built with Vite, plus a separate FastAPI backend. The current frontend reads local mock data; it is not yet connected to the backend API.

## Run the frontend locally

```bash
cd frontend
npm install
npm run dev
```

Create a production build with:

```bash
cd frontend
npm run build
```

The build output is written to `frontend/dist`.

## Deploy the frontend to Vercel

Deploy the `frontend` directory as its own Vercel project:

1. Import this repository in Vercel.
2. Set **Root Directory** to `frontend`.
3. Select the **Vite** framework preset (or let Vercel detect it).
4. Use `npm run build` as the build command and `dist` as the output directory. Vercel normally detects these from the Vite project.
5. Deploy. `frontend/vercel.json` includes the SPA rewrite so requests resolve to `index.html`.

Alternatively, from the `frontend` directory, authenticate with the Vercel CLI and run `vercel` for a preview deployment or `vercel --prod` for production.

## Backend

The FastAPI service in `backend/` is not deployed by this frontend configuration, and the frontend currently uses mock data rather than calling the API. Host the backend separately before switching the UI to live data; configure production database credentials, JWT secrets, LLM credentials, and CORS origins for that host. Do not expose secrets through Vite `VITE_*` variables, since those are included in the browser bundle.
