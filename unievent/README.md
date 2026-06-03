# UniEvent

UniEvent is a React + Vite event discovery experience built for university users. It combines a polished landing page, live Ticketmaster event listings, a featured event highlight, media gallery, and a registration modal into a single responsive front end.

## Features

- Animated hero section with search input for filtering events
- Featured event spotlight with a direct registration action
- Live event listings powered by the Ticketmaster Discovery API
- Event cards with venue, city, date, image, and description data
- Registration modal for quick sign-up flow
- Media gallery and footer sections to complete the landing page
- Responsive layout with decorative motion and visual dividers

## Tech Stack

- React 18
- Vite
- Framer Motion
- React Icons
- react-intersection-observer
- Tailwind CSS and custom CSS utilities

## Getting Started

### Prerequisites

- Node.js 18 or newer
- npm
- A Ticketmaster Discovery API key

### Install

```bash
npm install
```

### Environment Variables

Create a `.env` file in the project root and add your Ticketmaster key:

```bash
VITE_TICKETMASTER_KEY=your_ticketmaster_consumer_key_here
REACT_APP_TICKETMASTER_KEY=your_ticketmaster_consumer_key_here
```

The app reads either variable name, but `VITE_TICKETMASTER_KEY` is the preferred Vite format.

### Run Locally

```bash
npm run dev
```

### Build

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

## Project Structure

- `src/App.jsx` wires together the full page layout
- `src/components/` contains the hero, listings, gallery, modal, footer, and supporting UI pieces
- `src/hooks/useEvents.js` handles Ticketmaster fetching and event normalization
- `public/` contains static assets

## Deployment

The repository includes an AWS EC2 + Nginx deployment guide in [DEPLOY.md](DEPLOY.md). It covers:

- Installing Node.js and Nginx on Ubuntu EC2
- Building the app for production
- Copying the build output to `/var/www/unievent`
- Configuring the included [nginx.conf](nginx.conf)
- Restarting Nginx after updates

## Notes

- The app filters out irrelevant or ad-like events from the API results.
- If the API key is missing, the event list will not load and the UI will display an error message.
- The build output is generated into `build/`.
