# Keel: habits, journal, focus and days-since counters

An installable web app (PWA) that runs offline on Android and Linux. It includes:

- **Today**: your habits due today, a task list, a quick mood check-in, the focus timer and your counters on one screen
- **Habits**: choose which days each habit repeats on, tick the last 7 days, and see streaks, your best streak, a 30-day completion rate and an 18-week heatmap
- **Focus**: a Pomodoro timer with focus, short-break and long-break lengths you can set, session labels, a chime, keep-screen-on, a session log and a 7-day chart
- **Journal**: one entry per day, a mood scale, writing prompts, search, a 30-day mood strip and a writing streak
- **Days since**: live counters for bad habits you're quitting, with milestones, your best run, and a reset history with notes
- **Settings**: system/light/dark theme, backup export/import (merges), notifications, and an option to erase everything

All data is stored on the device you're using, and nothing is sent anywhere.

---

## 1. Put it online (free, about 5 minutes, done once)

An app has to be served over HTTPS before a phone will install it. GitHub Pages does this for free.

1. Go to github.com and create a **new public repository**, for example `keel`.
2. Click **"uploading an existing file"** and drag in everything from this folder: all the files (`index.html`, `manifest.webmanifest`, `sw.js`, the four `.png` icons and `README.md`). Commit.
   - From the terminal instead:
     ```bash
     cd keel
     git init && git add . && git commit -m "Keel app"
     git branch -M main
     git remote add origin https://github.com/<your-username>/keel.git
     git push -u origin main
     ```
3. In the repo, go to **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, then choose branch **main** and folder **/ (root)**. Save.
4. After a minute or so your app is live at `https://<your-username>.github.io/keel/`.

## 2. Install on the Honor Magic V5

1. Open the link in **Chrome**.
2. Tap the **⋮ menu → Add to home screen → Install** (if Chrome shows an "Install app" banner, you can tap that instead).
3. Keel now has its own icon and opens full-screen like any other app. Long-press the icon for shortcuts to Focus, Journal and Habits.
4. The layout adapts when you unfold: the cover screen shows a bottom tab bar, and the inner screen switches to a side rail with two columns.

**For the focus timer:** MagicOS is aggressive about putting background apps to sleep. For the alarm to go off on time, keep Keel open (the "Keep the screen on" setting is on by default). If the phone does put it to sleep, the finished session is still logged when you come back. You can also go to Settings → Battery → App launch → Keel (or Chrome) → Manage manually and allow it to run in the background.

## 3. Install on Kubuntu

1. Open the link in **Chrome, Chromium, Brave or Edge**. Firefox on Linux can't install web apps.
2. Click the **install icon** at the right end of the address bar, or go to ⋮ → *Cast, save and share* → *Install page as app*.
3. Keel shows up in the KDE application launcher and can be pinned to the taskbar.
4. On a keyboard, the **space bar** starts and pauses the focus timer.

## Moving data between phone and laptop

Each device keeps its own data. To copy it across:

1. On one device, open **Settings (gear) → Export backup** (on the phone you can also use **Share backup** to send it via Quick Share, email or Drive).
2. On the other device, open **Settings → Import and merge** and pick the file.

Importing **merges** the backup with what's already there, so habits, ticks, counters, tasks and focus sessions from both devices are kept, and anything you deleted stays deleted. If you wrote a journal entry for the same day on both devices, the most recently edited one wins.

Exporting a backup now and then is also a good safety net in case you clear your browser data.

## Updating the app

Edit `index.html`, change `VERSION` in `sw.js` (e.g. `keel-v2`), and push or upload again. Installed copies pick up the new version the next time they're opened online. Your data isn't affected.
