# Pomodoro App

Desktop Pomodoro timer built with React, TypeScript, Vite, and Electron.

The app has a regular timer view and a compact always-on-top mode for keeping the timer visible while working in other apps.

## Web Version

The browser version is a landing page with an online timer demo. It is deployed to GitHub Pages from the `main` branch.

The true always-on-top mode is available in the desktop app because browsers do not reliably support keeping a page above every other app window.

## Features

- Focus, short break, and long break timer modes.
- Compact always-on-top window mode with a 16:9 layout.
- Start, pause, reset, and skip controls.
- Synthesized completion sound when a timer finishes.
- Completed focus-session counter for the current day.
- Daily stats reset after 05:00 local time.
- Local state persistence between launches.
- Desktop builds for macOS, Windows, and Linux through Electron Builder.

## Development

Install dependencies:

```bash
npm install
```

Run the app in development mode:

```bash
npm run dev
```

This starts the Vite renderer and the Electron desktop shell together.

## Scripts

- `npm run dev` starts the local development app.
- `npm run build` type-checks and builds the renderer and Electron files.
- `npm run lint` runs ESLint.
- `npm run start` starts Electron from the built Electron entrypoint.
- `npm run dist` builds the app and packages desktop installers.

## Deployment

GitHub Pages is configured with `.github/workflows/deploy.yml`. The workflow builds `dist` with the `/pomodoro-app/` base path and publishes it as the web app.

Desktop downloads should be attached to GitHub Releases after running `npm run dist`.

## Build Output

Generated folders are ignored by git:

- `dist` for the Vite renderer build.
- `electron-dist` for compiled Electron files.
- `node_modules` for installed dependencies.

## Tech Stack

- React 19
- TypeScript
- Vite
- Electron
- Electron Builder
