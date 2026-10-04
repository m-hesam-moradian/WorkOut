# 🏋️ CALISTHENICS BULK

> A polished, mobile-first personal workout application with set-by-set guidance, rest timers, history, music, and a fully editable plan. No backend, no login, no internet required — all data stored locally on your device.

<p align="center">
  <strong>Single File</strong> · 166 KB &nbsp;|&nbsp;
  <strong>Storage</strong> · localStorage &nbsp;|&nbsp;
  <strong>Offline</strong> · 100%
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML-vanilla-4FD1C7?style=for-the-badge&logo=html5&logoColor=white" alt="HTML">
  <img src="https://img.shields.io/badge/CSS-neumorphic-243240?style=for-the-badge&logo=css3&logoColor=white" alt="CSS">
  <img src="https://img.shields.io/badge/JS-vanilla-F6A623?style=for-the-badge&logo=javascript&logoColor=white" alt="JS">
  <img src="https://img.shields.io/badge/Storage-localStorage-5EEAD4?style=for-the-badge&logo=googlesheets&logoColor=white" alt="localStorage">
</p>

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Weekly Schedule](#-weekly-schedule)
- [Quick Start](#-quick-start)
- [How to Use](#-how-to-use)
- [Data Storage](#-data-storage)
- [Customization](#-customization)
- [File Location](#-file-location)
- [Browser Support](#-browser-support)
- [Privacy](#-privacy)
- [License](#-license)

---

## 📖 Overview

**Calisthenics Bulk** is a single-file workout tracker built for mobile-first use. It preserves a 5-day calisthenics program (Saturday → Wednesday training, Thursday backup, Friday recovery) with the original exercises, skill progressions, and Cindy AMRAP challenge — and wraps it in a guided, set-by-set workout experience with:

- Rest timers with beep + vibration
- Per-set reps and duration history
- In-app YouTube music player
- Media link attachments per exercise (form videos, images)
- JSON plan sharing between users
- Smart Thursday backup that auto-detects missed workouts

Everything runs locally in your browser. **No backend, no database, no login, no internet connection required** after first load. Your profile, workout plan, history, music playlist, and active workout state all persist in `localStorage` — so they remain tomorrow, next week, even after restarting your phone.

---

## ✨ Features

### 🎯 Set-by-Set Workout Mode
The app coaches you through every set: `Start Set` → timer counts up → enter reps → `Done` → rest timer auto-starts with beep + vibration → next set prompt. Per-set reps and durations are stored separately — never collapsed into a single total.

### ⏱️ Rest Timer Controls
`+15s` / `-15s` / `Pause` / `Skip` — adjustable per set. Beep via Web Audio API + `navigator.vibrate()` when rest completes. Set timer never starts automatically — only when you press Start Set.

### 📊 Per-Set Reps & Duration
Every individual set is stored separately. `Pull-ups: 7 / 6 / 5` with per-set durations (`18s / 16s / 15s`) so you can track fatigue across sets.

### 🔄 Resume After Refresh
Refresh mid-workout? No problem. The active workout state saves continuously. On reopen, a yellow "Workout in progress" banner offers **Resume** or **Discard**. `beforeunload` warns you if you try to leave.

### 🏆 Cindy 20-min AMRAP
Tuesday's Cindy workout gets its own flow: 20-minute countdown, +/− round counter, finish-early option, saved as a special Cindy entry in history. Scheme: `5 pull-ups · 10 push-ups · 15 air squats` per round.

### 🎯 Skill Tracking
Handstand and muscle-up progression stay skill-based (not forced into hypertrophy sets). Record practice time, milestone stage, and notes. Wednesday lets you pick ONE skill milestone to focus on.

### ✏️ Fully Editable Plan
Add / remove / rename / reorder exercises. Change sets, rest duration, exercise type (`strength` / `timed` / `skill`). Edit workout names per day. Stable exercise IDs keep history intact even when names change.

### 🎵 In-App Music Player
Paste any YouTube link — it plays inside the app via YouTube IFrame API. Pre-loaded with motivational gym mixes. Play / pause / skip / add / remove. Mini now-playing bar floats during workouts.

### 🔗 Media Links Per Exercise
Each exercise supports YouTube / image / video / link URLs. Rendered as tappable chips in the day overview and the active workout "Get Ready" screen — so you can pull up a form video before each set.

### 📤 JSON Plan Sharing
Download your workout plan as a portable JSON file — contains ONLY the program (no personal data). Send it to a friend; they Import Plan on their device. Profile and history stay completely separate.

### 🤖 Thursday Smart Backup
Thursday auto-detects which workouts you missed this week and suggests the first missed day as the primary catch-up. Other missed days appear as smaller chips. Or tap `Just Rest Today` to log recovery instead.

### 🗑️ Full Backup / Reset
Export everything (profile + plan + history + settings + active workout) as a single JSON backup. Import to restore on any device. Reset Application wipes everything with a confirmation modal.

---

## 📅 Weekly Schedule

The default program — fully editable in the Plan tab.

| Day | Workout | Details |
|-----|---------|---------|
| **Sat** | Push + Handstand | 4 strength + 1 skill · 5 exercises · 13 sets |
| **Sun** | Pull + Muscle-up | 5 strength + 1 skill · 6 exercises · 16 sets |
| **Mon** | Legs + Core | 6 exercises · 18 sets · includes timed Plank |
| **Tue** | Cindy 20-min AMRAP | 5 pull-ups · 10 push-ups · 15 air squats per round |
| **Wed** | Full Body + Skill | 6 strength + 1 skill milestone · 7 exercises |
| **Thu** | Backup / Rest | Smart catch-up day · auto-detects missed workouts |
| **Fri** | Free / Recovery | No training · recovery is when adaptation happens |

---

## 🚀 Quick Start

Get up and running in under 30 seconds.

### 1. Open the file
Double-click `calisthenics_bulk_tracker.html` or drag it into any modern browser (Chrome, Firefox, Safari, Edge). Works on desktop, tablet, and phone.

### 2. Enter your name
A welcome popup appears on top of the dashboard. Type your name and tap **Continue**. The popup disappears, and the dashboard is ready. You will never be asked again unless you reset the app.

### 3. Tap today's workout
The Home tab shows today's workout card with a glowing **Start Workout** button. Tap it to enter workout mode.

### 4. Follow the coach
Press **Start Set** → do the reps → enter the number → tap **Done** → rest timer auto-starts with a beep → next set appears. Repeat for every set of every exercise.

### 5. Finish & review
When all sets are done, a completion screen shows total duration, sets, reps, and your best set. Tap **Done** → returns to Home. The workout is now in your History.

---

## 📱 How to Use

Five main areas — navigate via the bottom tab bar.

### 🏠 Home · Dashboard
Greets you by name + today's date. Shows today's workout card with exercise/set counts and a prominent Start button. Below: weekly plan list — today's row glows cyan. If a workout was left in progress, a yellow Resume banner appears.

### 💪 Workout · Active Session
Focused single-screen flow: exercise name, set number (1/3), previous result for that exact set, large timer, reps input, Done button. Rest screen shows countdown with `+15s` / `-15s` / `Pause` / `Skip` controls. Tap **Pause** to freeze the whole session.

### 📜 History · Past Workouts
List of completed workouts (newest first). Each card shows date, day, workout name, duration, total sets/reps, per-exercise rep strings with green/red delta vs your previous workout for that day. Tap any card to expand per-set details.

### 📋 Plan · Edit & Share
Tab through the 7 days. Edit workout name, add/remove/rename/reorder exercises, change sets / rest / type / stable ID, attach YouTube/image/video links. Save Plan persists. **Download Plan** exports portable JSON; **Import Plan** restores from a friend's file.

### 👤 Profile · Settings & Data
Edit your name. Toggle sound / vibration. **Export All Data** (full backup), **Import All Data** (restore), **Reset Application** (wipes everything with confirmation). Shows total workouts logged.

### 🎵 Music Player
Tap the music icon (♪) in the top bar to open the music panel. Pre-loaded with 3 motivational gym mixes. Paste any YouTube link to add your own. Plays in-app via YouTube IFrame API — a mini now-playing bar floats at the bottom during workouts so you can control it without leaving the workout screen. Tap any track to play, × to remove. Playlist persists in `localStorage`.

---

## 💾 Data Storage

Five separate `localStorage` keys keep concerns isolated. Nothing expires.

| Key | Purpose |
|-----|---------|
| `cb_profile_v2` | Your name + account creation date. Never expires, never sent anywhere. |
| `cb_plan_v2` | The full program: days, exercises, sets, rest, media links. Editable in Plan tab. Exportable as portable JSON. |
| `cb_history_v2` | Array of completed workouts — per-set reps + durations + total volume. Drives the "Previous" target shown during new workouts. |
| `cb_active_v2` | In-progress workout state. Enables resume after refresh, app close, or phone restart. Cleared on completion. |
| `cb_settings_v2` | Sound on/off, vibration on/off. Toggleable from Profile tab or the top-bar sound icon. |
| `cb_music_v2` | Your custom music playlist. Pre-seeded with 3 motivational mixes. Add/remove tracks via the music panel. |

### Example Workout History Entry

```json
// Stored in cb_history_v2
{
  "date": "2026-10-04",
  "day": "sunday",
  "workoutName": "Pull + Muscle-up",
  "durationSec": 2538,
  "type": "strength",
  "totalSets": 16,
  "totalReps": 84,
  "exercises": [
    {
      "id": "pullups",
      "name": "Pull-ups",
      "sets": [
        { "reps": 7, "durationSec": 18 },
        { "reps": 6, "durationSec": 16 },
        { "reps": 5, "durationSec": 15 }
      ]
    }
  ]
}
```

---

## 🎨 Customization

Make the program yours — no code edits needed.

### A. Edit exercises
**Plan tab** → tap a day → rename exercises, change set counts, adjust rest seconds, change type (`strength` / `timed` / `skill`), reorder with ↑/Down buttons, remove with ×. Add new exercises with the + button. Don't forget to tap **Save Plan**.

### B. Attach form videos
In the Plan editor, each exercise has a **Media Links** section with YouTube / Image / Video / Link URL fields. Paste a YouTube tutorial URL — it appears as a tappable chip on the day overview and the active workout Get Ready screen.

### C. Configure Thursday & Friday
Thursday is a smart backup day by default — it auto-suggests your first missed workout. Friday is pure recovery. You can keep them as rest, or convert them into regular training days via the Plan editor.

### D. Build your playlist
Tap the music icon in the top bar. The default 3 tracks are motivational gym mixes — replace them with your own. Paste any YouTube link (watch URL, youtu.be, shorts, embed, or raw video ID). Tracks auto-play when added.

### E. Share your plan
**Plan tab** → scroll to "Share Your Plan" card → **Download Plan**. The exported JSON contains ONLY the workout program — no profile, no history, no personal data. Send the file to a friend; they tap **Import Plan** on their device.

---

## 📁 File Location

Single self-contained HTML file — no dependencies, no install.

```
calisthenics_bulk_tracker.html   ← The app (166 KB)
README.md                        ← This file
```

Open `calisthenics_bulk_tracker.html` in any browser. Works offline after first load. All data stays in that browser's `localStorage`.

---

## 🌐 Browser Support

| Browser | Minimum Version |
|---------|----------------|
| Chrome | 90+ |
| Firefox | 88+ |
| Safari | 14+ |
| Edge | 90+ |
| Mobile Safari (iOS) | 14+ |
| Chrome Android | 90+ |

Requires JavaScript enabled. No frameworks — pure vanilla HTML/CSS/JS.

### Mobile First
Designed for phones. Bottom tab nav, large 44px+ tap targets, safe-area insets for notched devices, no horizontal scroll. Works great on tablet and desktop too.

### No Internet Needed
After first load, works fully offline. YouTube music playback requires internet (loads YT IFrame API). Everything else — workout tracking, history, plan editing, data export — works offline.

---

## 🔒 Privacy

- ✅ **Zero tracking** — no analytics, no cookies, no telemetry
- ✅ **Zero external API calls** (except YouTube for music playback)
- ✅ **Your workout data never leaves your device** unless you explicitly export it
- ✅ **No account, no login, no email required** — just a local profile with your name
- ✅ **Reset Application** wipes everything instantly

---

## 📄 License

This project is provided as-is for personal use. Modify it, share it, make it yours.

---

<p align="center">
  <strong>Built with vanilla HTML · CSS · JavaScript</strong><br>
  <sub>Calisthenics Bulk — Workout Tracker · v 2.0</sub>
</p>
