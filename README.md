# King's Gambit - Quiz Game Platform

King's Gambit is a modern, high-intensity quiz game platform built with performance and security in mind. It features a sleek, dark-themed dashboard for administrators and a real-time, responsive interface for participants.

## 🚀 Key Features

- **Admin Control Center**: A comprehensive dashboard to manage questions, teams, game flow, and live statistics.
- **Participant Interface**: A glassmorphism-inspired UI designed for focus and speed, with real-time syncing.
- **Real-Time Syncing**: Uses `BroadcastChannel` for zero-latency local preview syncing and periodic polling for remote state.
- **Cheat Protection**: Built-in tracking for tab-switching and window minimization violations.
- **D1 Database Integration**: Persistent storage for teams, questions, scores, and violations using Cloudflare D1.
- **Custom Modals**: Elegant, themed alternatives to native browser alerts, confirms, and prompts.
- **Leaderboard**: Live, rank-based leaderboard with automatic updates and custom overlays.

## 🛠️ Tech Stack

- **Frontend**: Vanilla HTML5, CSS3 (Custom Design System), JavaScript (ES6+)
- **Backend**: Cloudflare Workers
- **Database**: Cloudflare D1 (SQLite-based)
- **Icons**: Font Awesome 6
- **Typography**: Outfit (Google Fonts)

## 📁 Project Structure

```text
King's Gambit/
├── admin.html          # Admin panel interface
├── index.html          # Login page
├── quiz.html           # Participant game screen
├── leaderboard.html    # Standalone leaderboard
├── preview.html        # Live question preview
├── css/                # Stylesheets
│   ├── admin.css       # Admin-specific styles
│   ├── participant.css # Quiz screen styles
│   └── global.css      # Core variables and shared UI
├── js/                 # Logic
│   ├── admin.js        # Admin dashboard logic
│   ├── participant.js  # Participant-side logic
│   └── modals.js       # Shared custom modal system
└── worker/             # Backend
    └── worker.js       # Cloudflare Worker API logic
```

## ⚙️ Setup & Deployment

### 1. Database Setup (Cloudflare D1)
Create a D1 database in your Cloudflare dashboard and run the necessary schema migrations (available in the system logs).

### 2. Worker Configuration
- Deploy `worker/worker.js` to Cloudflare Workers.
- Set the following environment variables in your Worker:
  - `ADMIN_PASSWORD`: For admin dashboard access.
  - `ADMIN_IP`: (Optional) For IP-restricted admin panel.

### 3. Frontend Configuration
Update the `WORKER_URL` in `js/admin.js`, `js/participant.js`, and `js/login.js` (or via a central `env.js` if configured) to point to your deployed Worker.

## 🕹️ Usage

1.  **Preparation**: Upload your questions via a JSON file in the Admin settings.
2.  **Registration**: Teams log in using unique passkeys generated/added in the Admin panel.
3.  **Gameplay**: The Administrator controls the flow (Questions, Options, Timer, Answers) from the Control Center.
4.  **Monitoring**: Track violations and live scores in real-time.

---

Built for **TRAIN 303**. All Rights Reserved.
