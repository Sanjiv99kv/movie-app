# Movie App

A Netflix-style movie and TV discovery app built with React, Redux, and Tailwind CSS. Browse trending content, explore movies and shows, search titles, and view detailed pages with cast, ratings, trailers, and recommendations — powered by [The Movie Database (TMDB)](https://www.themoviedb.org/) API.

**Live demo:** [movie-app-seven-gilt.vercel.app](https://movie-app-seven-gilt.vercel.app/)

## Features

- **Home** — Trending banner carousel plus horizontal rows for now playing, top rated, popular TV, and on-the-air shows
- **Explore** — Browse movies or TV shows with infinite scroll pagination
- **Search** — Multi-search across movies and TV with load-more results
- **Details** — Poster, backdrop, ratings, runtime, cast, writer, overview, and similar/recommended titles
- **Trailers** — Play official videos from TMDB
- **Responsive UI** — Desktop header navigation and mobile bottom nav

## Tech Stack

- [React](https://react.dev/) 18
- [Vite](https://vitejs.dev/) 5
- [Redux Toolkit](https://redux-toolkit.js.org/) & [React Redux](https://react-redux.js.org/)
- [React Router](https://reactrouter.com/) 6
- [Tailwind CSS](https://tailwindcss.com/) 3
- [Axios](https://axios-http.com/) — TMDB API requests
- [Moment.js](https://momentjs.com/) — Date formatting
- [React Icons](https://react-icons.github.io/react-icons/)

## Prerequisites

- [Node.js](https://nodejs.org/) (v18+ recommended)
- npm
- A free [TMDB API](https://www.themoviedb.org/settings/api) access token (v4 read token)

## Getting Started

1. **Clone the repository**

   ```bash
   git clone <your-repo-url>
   cd MovieApp
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Configure the API token**

   Create a `.env` file in the project root:

   ```env
   REACT_APP_TOKEN=your_tmdb_v4_read_access_token
   ```

   Get your token from [TMDB Settings → API](https://www.themoviedb.org/settings/api).

   > **Note:** The app currently reads the token from `src/main.jsx`. For local development, ensure your token is set there or refactor to use `import.meta.env` with a `VITE_`-prefixed variable.

4. **Run the development server**

   ```bash
   npm run dev
   ```

   Open the URL shown in the terminal (typically `http://localhost:5173`).

## Available Scripts

| Command           | Description                    |
| ----------------- | ------------------------------ |
| `npm run dev`     | Start Vite dev server          |
| `npm run build`   | Production build to `dist/`    |
| `npm run preview` | Preview the production build   |
| `npm run lint`    | Run ESLint on the project      |

## Routes

| Path              | Page        | Description                          |
| ----------------- | ----------- | ------------------------------------ |
| `/`               | Home        | Trending banner and content rows     |
| `/movie`          | Explore     | Discover movies (infinite scroll)    |
| `/tv`             | Explore     | Discover TV shows                    |
| `/:explore/:id`   | Details     | Movie or TV show detail page         |
| `/search`         | Search      | Search movies and TV (`?q=query`)    |

## Project Structure

```
MovieApp/
├── public/
├── src/
│   ├── components/     # Header, Footer, Card, Banner, VideoPlay, etc.
│   ├── constant/       # Navigation config
│   ├── hook/           # useFetch, useFetchDetails
│   ├── pages/          # Home, Explore, Detail, Search
│   ├── store/          # Redux store and movie slice
│   ├── App.jsx         # Routes and global data fetch
│   └── main.jsx        # Entry point, axios + TMDB config
├── index.html
├── tailwind.config.js
└── vite.config.js
```

## Deployment

The project is deployed on [Vercel](https://vercel.com/). After `npm run build`, deploy the `dist/` folder or connect the repo to Vercel for automatic deployments.

## API

All movie and TV data comes from the TMDB API (`https://api.themoviedb.org/3/`). Image URLs are loaded from TMDB’s configuration endpoint.

## License

This project is for learning and portfolio use. TMDB data and images are subject to [TMDB’s terms of use](https://www.themoviedb.org/terms-of-use).
