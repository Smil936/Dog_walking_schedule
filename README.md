# 🐾 Dog Walk Scheduler

A weekly dog walk scheduling app that connects to Google Sheets for persistent tracking.

---

## Setup Guide

### Step 1 — Put index.html on GitHub Pages

1. Create a new GitHub repository (e.g. `dog-walk-scheduler`)
2. Upload `index.html` to the root of the repo
3. Go to **Settings → Pages → Source** and select `main` branch, `/ (root)`
4. Your app will be live at https://smil936.github.io/Dog_walking_schedule

---

### Step 2 — Set up Google Apps Script

This is the bridge between your app and Google Sheets. It only takes a few minutes.

1. Open your Google Sheet:
   https://docs.google.com/spreadsheets/d/15EAjRXNrSoIW2IRVqwR18SkgVOLULeQdG8pEi5csfXU

2. Click **Extensions → Apps Script**

3. Delete everything in the editor and paste the entire contents of `Code.gs`

4. Click **Save** (the floppy disk icon), name the project `DogWalkScheduler`

5. Click **Deploy → New deployment**

6. Click the gear icon next to "Type" and select **Web app**

7. Fill in:
   - Description: `Dog Walk Scheduler API`
   - Execute as: **Me**
   - Who has access: **Anyone** ← important, this is what allows your app to talk to it

8. Click **Deploy**

9. You'll be asked to authorize — click through the Google permissions (it's your own script accessing your own sheet)

10. Copy the **Web app URL** — it looks like:
    `(https://script.google.com/macros/s/AKfycbywORsPagJLfc2KNBCBNeHO_gRYu-MM-TcNraFSKNIrzg3vVpZ3k2Fy9lcRKyUEnZ05/exec)`

---

### Step 3 — Connect the app to your sheet

1. Open your app (GitHub Pages URL or just open `index.html` locally)
2. In the **Google Sheets** panel on the left, paste your Web App URL
3. Click **Test** — you should see "✓ Connected to Google Sheets!"
4. The URL is saved in your browser automatically for future visits

---

## How to use

### Weekly workflow
- Set the **Current week** label at the top (e.g. "Week of 26 May 2026")
- Add your dogs, schedule them, then click **💾 Save Week**
- Next week, change the week label and start fresh — previous weeks are saved in Sheets
- Click **📅 Load Week** to browse and reload any past week

### Google Sheet structure
The script automatically creates 3 tabs in your sheet:
- **Weeks** — one row per saved week with totals
- **Dogs** — each dog's details per week
- **Schedule** — each booked session per week

### Rates
- Solo walk, 1 session: **$20**
- Group walk (any sessions): **$15/walk**
- Solo walk, 3 sessions: **$50 package**

---

## Re-deploying after changes to Code.gs

If you ever edit the Apps Script code:
1. Click **Deploy → Manage deployments**
2. Click the pencil/edit icon
3. Change version to **New version**
4. Click **Deploy**

The URL stays the same so you don't need to update the app.
