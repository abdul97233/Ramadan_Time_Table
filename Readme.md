<p align="center">
  <img src="https://via.placeholder.com/1200x400/0A2E35/D4A843?text=Ramadan+Timings+%E2%98%AA+Nepal" alt="Ramadan Timings Banner"/>
</p>

<h1 align="center">☪ Ramadan Timings – Nepal 🇳🇵</h1>

<p align="center">
  🌙 Sehri • 🌅 Iftar • 🕌 Prayer Times • 📅 30 Days • 🎵 Nasheeds • ⚙ Admin Panel
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Responsive-Mobile%20%2B%20Desktop-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Backend-Optional-orange?style=for-the-badge"/>
</p>

---

# 🌙 Ramadan Timings Web App

A beautifully designed **Ramadan Sehri & Iftar Timing Application** with:

- 🇳🇵 Live Nepal Time (UTC +5:45)
- 📅 30-Day Ramadan Schedule
- ⏳ Smart Countdown
- 🕌 Prayer Times
- 🎵 Built-in Nasheed Player
- ⚙ Powerful Admin Panel
- 📱 Fully Responsive
- 💾 LocalStorage Persistence
- 🌌 Animated Night Theme

No framework. No dependency. Pure HTML, CSS & JavaScript.

---

# ✨ Features

## 🌍 Live Nepal Clock
- Real-time NPT clock
- Auto Hijri date display
- Ramadan progress bar
- Daily auto-refresh without reload

---

## ⏳ Smart Countdown
Automatically switches between:
- 🌙 Sehri
- 🌅 Iftar
- 🌙 Tomorrow Sehri

Updates every second.

---

## 📅 30-Day Ramadan Schedule
- Preloaded Mirchaiya (Nepal) schedule
- Highlights today
- Shows tomorrow preview
- Editable from Admin Panel

---

## 🕌 Prayer Times
Includes:
- Fajr
- Dhuhr
- Asr
- Maghrib
- Isha

Automatically highlights the next prayer.

---

## 🎵 Ramadan Nasheed Player
- Playlist system
- Play / Pause / Next / Previous
- Volume slider
- Progress seek bar
- Wave animation
- Web Audio fallback

To add custom music:

```js
const TRACKS = [
  {
    name: "Your Nasheed",
    artist: "Artist Name",
    url: "https://yourdomain.com/audio.mp3",
    dur: "3:45"
  }
];
```

---

# 🔐 Admin Panel

Default Password:

```
ramadan2025
```

### Admin Features

### ⚙ General
- Change city
- Change Ramadan start date
- Default Sehri / Iftar

### ⏰ Today
- Instantly override today's timings

### 📅 30-Day Manager
- Edit each day
- Bulk fill
- Auto shift (±1 min/day)
- Copy down feature
- Jump to day

### 🕌 Prayer Times
Edit all five daily prayers

### 🔐 Security
- Change password
- Reset all data

---

# 📸 Preview

Create a folder:

```
/screenshots
```

Then add images:

```md
## 🌙 Main Dashboard
![Main](screenshots/main.png)

## 📅 30-Day Schedule
![Schedule](screenshots/schedule.png)

## ⚙ Admin Panel
![Admin](screenshots/admin.png)

## 🎵 Music Player
![Music](screenshots/music.png)
```

---

# 🚀 Live Deployment Guide

## 🌐 Deploy on Netlify (Fastest)

### Option 1 – Drag & Drop
1. Go to https://app.netlify.com/drop
2. Drag project folder
3. Done 🎉

---

### Option 2 – GitHub Auto Deploy
1. Push to GitHub
2. Connect repo in Netlify
3. Publish directory:
```
/
```

No build command needed.

---

## 🌐 Deploy on Vercel

1. Push project to GitHub
2. Import project on https://vercel.com
3. Deploy

No configuration required.

---

# 📦 Upgrade to PWA (Install as App)

## 1️⃣ Create manifest.json

```json
{
  "name": "Ramadan Timings Nepal",
  "short_name": "Ramadan",
  "start_url": ".",
  "display": "standalone",
  "background_color": "#050F14",
  "theme_color": "#D4A843",
  "icons": [
    { "src": "icon-192.png", "sizes": "192x192", "type": "image/png" },
    { "src": "icon-512.png", "sizes": "512x512", "type": "image/png" }
  ]
}
```

Add inside `<head>`:

```html
<link rel="manifest" href="manifest.json">
<meta name="theme-color" content="#D4A843">
```

---

## 2️⃣ Create service-worker.js

```js
self.addEventListener('install', e => {
  e.waitUntil(
    caches.open('ramadan-cache').then(cache => {
      return cache.addAll(['/', '/index.html']);
    })
  );
});

self.addEventListener('fetch', e => {
  e.respondWith(
    caches.match(e.request).then(res => res || fetch(e.request))
  );
});
```

---

## 3️⃣ Register Service Worker

Add before `</body>`:

```html
<script>
if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('service-worker.js');
}
</script>
```

Now users can install it like a mobile app 📱

---

# 🔗 Backend Version (Node + MongoDB)

If you want multi-city + database support:

## Install

```bash
npm init -y
npm install express mongoose cors dotenv
```

---

## server.js

```js
const express = require('express');
const mongoose = require('mongoose');
const cors = require('cors');
require('dotenv').config();

const app = express();
app.use(cors());
app.use(express.json());

mongoose.connect(process.env.MONGO_URI);

app.get('/', (req,res)=>res.send("Ramadan API Running"));

app.listen(5000, () => console.log('Server running on port 5000'));
```

---

## Folder Structure

```
ramadan-pro/
│
├── client/
│   └── index.html
│
├── server/
│   ├── server.js
│   ├── models/
│   └── routes/
│
└── package.json
```

---

# 💾 Data Storage

Stored in:

```
localStorage → ramadanConfig
```

Reset:
- Admin → Reset
OR
- Clear browser storage

---

# 📆 Default Configuration

- 📍 Mirchaiya, Nepal
- 📅 Ramadan 1446 AH
- 🗓 Feb 19 – Mar 20, 2026
- 🌙 Preloaded 30 days

---

# 🔮 Future Enhancements

- API auto-fetch prayer times
- Azan notifications
- Push notifications
- Multi-city selector
- Hijri auto sync
- Cloud database

---

# 📜 License

Free for personal & educational use.

---

# ☪ Ramadan Kareem

May Allah accept your fasts and duas.

If you like this project, please ⭐ star the repository.
