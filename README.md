<div align="center">

# Anime Vault

Discover popular anime with smooth server-rendered pages, infinite scrolling, and delightful motion.

![preview](./public/hero.png)

[![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-18-61dafb?logo=react&logoColor=061d2a)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178c6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-38b2ac?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-000?logo=vercel)](https://vercel.com/)

</div>

---

### ✨ Features

- **Server Components + Server Actions**: Fast, SEO-friendly data fetching on the server using Next.js 14.
- **Infinite Scroll**: Seamless pagination using `react-intersection-observer`.
- **Framer Motion Animations**: Subtle fade-in cards powered via a `MotionDiv` wrapper.
- **Tailwind CSS Styling**: Utility-first styles with a custom hero background and dark theme.
- **Image Optimization**: Remote images allowed via `next.config.js` with `remotePatterns`.

### 🧰 Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **UI**: React 18, Tailwind CSS
- **Animations**: framer-motion (via `motion` package import)
- **Utilities**: `react-intersection-observer`

### 📂 Project Structure

```text
.
├─ app/
│  ├─ _data.ts               # Static sample data (not used by API calls)
│  ├─ action.tsx             # Server Action: fetches anime and returns cards
│  ├─ globals.css            # Tailwind base + global styles
│  ├─ layout.tsx             # Root layout with Hero and Footer
│  └─ page.tsx               # Home page: server-rendered initial grid
├─ components/
│  ├─ AnimeCard.tsx          # Anime card with motion + image + meta
│  ├─ Footer.tsx             # Footer with social icons
│  ├─ Hero.tsx               # Landing hero with headline and artwork
│  ├─ LoadMore.tsx           # Client component handling infinite scroll
│  └─ MotionDiv.tsx          # Re-export of framer-motion div
├─ public/                   # Static assets (icons, hero images)
├─ tailwind.config.ts        # Tailwind content paths + theme extensions
├─ next.config.js            # Next image remote patterns
├─ tsconfig.json             # TypeScript configuration
└─ package.json              # Scripts and dependencies
```

### 🚀 Getting Started

Prerequisites:

- Node.js 18+ and npm 9+ (or your preferred package manager)

Install dependencies:

```bash
npm install
```

Run the development server:

```bash
npm run dev
```

Open `http://localhost:3000` to view the app.

Build for production:

```bash
npm run build
npm start
```

### ⚙️ Configuration

- Tailwind is configured in `tailwind.config.ts` and loaded via `app/globals.css`.
- Remote images are enabled in `next.config.js` using permissive `remotePatterns`.
- The app fetches from the public Shikimori API. No API key is required.

### 📡 Data Fetching

- Initial page render calls the server action `fetchAnime(1)` in `app/action.tsx` and maps results to `AnimeCard` components server-side.
- Infinite scrolling uses `LoadMore` (client component). When the sentinel is in view, it calls `fetchAnime(page)` and appends new cards.

API endpoint used:

```
GET https://shikimori.one/api/animes?page={page}&limit=8&order=popularity
```

Notes:

- The API is public but may be subject to rate limiting. If you see throttling, slow down requests or add basic caching.

### 🎨 Styling & Motion

- Global dark theme set in `app/globals.css` with a custom `.red-gradient` utility.
- Hero background configured via Tailwind `backgroundImage` extension (`hero`).
- Animations use framer-motion; `MotionDiv` wraps `motion.div` for clean imports.

### 🧪 Scripts

```jsonc
{
  "dev": "next dev",
  "build": "next build",
  "start": "next start",
  "lint": "next lint"
}
```

Run linting:

```bash
npm run lint
```

### ☁️ Deployment

- Deploy on Vercel:
  - Push to a Git repository
  - Import the project on Vercel
  - Framework Preset: Next.js
  - Environment variables: none required

Other hosts supporting Node.js and Next.js 14 will also work.

### 🗺️ Roadmap Ideas

- Search and filter by genre, year, and rating
- Anime detail pages with episodes and casts
- Client-side caching and optimistic updates
- Skeleton loading states and error boundaries

### 🙌 Credits

- Data from the public `Shikimori` API (`https://shikimori.one`).
- Built with Next.js, React, TypeScript, Tailwind CSS, and framer-motion.

### 📄 License

This project does not currently include a license file. If you plan to open-source it, consider adding an OSI-approved license (e.g., MIT).
