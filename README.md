# Tetris

A playable, browser-based Tetris game built with Next.js, React, and Tailwind CSS. Stack falling tetrominoes, clear lines, and chase a high score — everything runs client-side with smooth animations and keyboard controls.

> Live demo: https://girishlade111.github.io/tetris/

## Features

- **Full Tetris gameplay** — 7 classic tetrominoes (I, O, T, S, Z, J, L) with rotation, soft drop, and hard drop
- **Scoring & levels** — points per line clear, level-ups that speed the fall, persistent high score
- **Next-piece preview** — see the upcoming tetromino
- **Pause / resume** — pause anytime without losing progress
- **Game over & restart** — instant restart from the game-over screen
- **Keyboard controls** — arrows/WASD-style movement, up/space to rotate and drop
- **Responsive design** — plays well on desktop and mobile screens
- **Dark UI theme** — shadcn/ui components with a custom Tetris board renderer

## Tech Stack

- **Framework:** Next.js 15 (App Router, static export)
- **Language:** TypeScript
- **UI:** React 19, Tailwind CSS, shadcn/ui (Radix primitives), Geist fonts
- **Icons:** lucide-react
- **Analytics:** @vercel/analytics (no-op on static export)

## Quick Start

```bash
# install dependencies
pnpm install

# run the dev server
pnpm dev
# open http://localhost:3000

# build the static site
pnpm build
# output goes to ./out
```

Requires Node.js 18+.

## Project Structure

```
.
├── app/                  # Next.js App Router
│   ├── layout.tsx        # Root layout (fonts, theme provider, analytics)
│   ├── page.tsx          # Home page — renders the game
│   └── globals.css       # Global Tailwind styles
├── components/
│   ├── ui/               # shadcn/ui primitives (buttons, dialogs, etc.)
│   └── theme-provider.tsx
├── lib/
│   └── utils.ts          # cn() class merge helper
├── public/               # Static assets
├── styles/
│   └── globals.css       # Additional global styles
├── tetris.tsx            # Main game component (board, pieces, scoring logic)
├── next.config.mjs       # next config (output: 'export', basePath for gh-pages)
└── tailwind.config.ts    # Tailwind config
```

## Controls

| Key | Action |
|---|---|
| ← / → | Move piece left / right |
| ↓ | Soft drop |
| ↑ | Rotate |
| Space | Hard drop |
| P | Pause / resume |

## Environment Variables

None required — the game is fully client-side.

## Deployment

This project builds to a static export (`output: 'export'`) and is deployed to **GitHub Pages** at https://girishlade111.github.io/tetris/.

```bash
pnpm build   # -> ./out
```

Note: `next.config.mjs` sets `basePath: '/tetris'` so asset URLs resolve under the GitHub Pages subpath. If you deploy to a root domain or Vercel instead, remove the `basePath` line.

## License

MIT — free to use and remix.

---

Built by Girish Lade — https://ladestack.in
