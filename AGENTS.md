# icon

## Cursor Cloud specific instructions

### Project overview
This branch contains a **Vue 3 + Vite** single-page app: a static, client-side login page (`欢迎登录`) for a smart-city management UI. There is **no backend, database, or external service** — "login" is a UI mockup (the form uses `@submit.prevent` and does not call any API).

Note: the default `main` branch is essentially empty (only `README.md`). The runnable app lives on feature branches (e.g. `cursor/figma-login-vue-e5e1`). A sibling branch (`cursor/responsive-login-page-c0ba`) holds a CDN-based static HTML variant with no build step.

### Commands
Standard scripts are defined in `package.json`:
- Dev server: `npm run dev` (Vite, serves on port `5173`)
- Production build: `npm run build` (outputs to `dist/`)
- Preview built app: `npm run preview` (port `4173`)

There are **no lint or test scripts** configured in this repo.

### Notes
- Node 22 + npm are preinstalled; `npm install` is handled by the startup update script (guarded so it is a no-op on the empty `main` branch).
- The Vite dev server binds to `localhost` only; pass `--host` if external access is needed.
