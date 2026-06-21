# Cashflow Compass — Install on your phone

Updated for **June 2026 data** (v1.1.0) — your salaries, EMIs, card balances and budgets are pre-loaded.

You have **three install paths**. Pick **Path A (GitHub Pages)** for a permanent free URL.

---

## Path A — GitHub Pages (recommended, ~10 min one-time setup)

A permanent free URL that never expires. Updates push instantly to your phone.

### One-time setup
1. Go to **https://github.com** and click **Sign up** (free, no credit card)
2. Pick a username, e.g. `ragil-rak`
3. Verify your email
4. Click the **+** (top right) → **New repository**
5. Repository name: `cashflow-compass` (or anything)
6. Set to **Public** (GitHub Pages requires public for free accounts)
7. Tick "Add a README file"
8. Click **Create repository**

### Upload your app files
1. In the new repo, click **Add file → Upload files**
2. Open File Explorer → drag all 6 files from `C:\Users\athir\Claude Project\Credit Cards\CashflowCompass\` into the GitHub upload area:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `apple-touch-icon.png`
3. Scroll down → click **Commit changes**

### Enable GitHub Pages
1. In the repo, click **Settings** (top right)
2. In left sidebar, click **Pages**
3. Under "Build and deployment" → "Branch" → select **main** → **/(root)** → click **Save**
4. Wait ~30 seconds. Refresh the page.
5. You'll see: **"Your site is live at https://ragil-rak.github.io/cashflow-compass/"**
6. **Copy that URL** — that's your permanent app URL.

### Install on phone (same as before)
1. WhatsApp/email the URL to yourself
2. Open in Chrome on Android
3. ⋮ menu → **Install app** → confirm
4. Cashflow icon now on home screen
5. ⚙️ Settings → Bill reminders → enable

### Updating the app later
Whenever I send a new version, you replace files in the GitHub repo:
1. Open the repo → click on `index.html` (the file you want to replace)
2. Click the pencil ✏️ icon (Edit) → **Delete file** at the bottom (or just paste new content)
3. Or easier: click **Add file → Upload files** → drag the new file (it overwrites)
4. Commit changes
5. Phone updates automatically next time you open the app (service worker fetches new version)

---

## Path B — Chrome direct (quickest test, no hosting)

1. Copy the `CashflowCompass` folder to your phone (USB cable / Google Drive / email zip)
2. Open `index.html` from phone File Manager → "Open with Chrome"
3. Tap ⋮ → **Add to Home screen**

Drawback: not a true PWA (no auto-update, no notifications, easier to lose data).

---

## Path C — Netlify Drop (1-hour temporary, the one you tried)

Quick deploy but URL expires in 1 hour unless you create a free Netlify account from the "Sign up to keep it" link.

---

## What's pre-loaded in v1.1.0

Based on your **June 2026 statements + manually-confirmed current outstanding balances**:

**Income**
- You: AED 9,250 / month
- Wife: AED 2,300 / month
- Pay day: 1st of month

**Rent**: AED 1,700 (set, change in Settings if needed)

**4 credit cards (current outstanding)**
- ENBD U By Emaar — AED 16,389.15 / 16,500 limit (⚠ 99% utilized)
- CBD ONE — AED 13,546.58 / 16,500
- Emirates Islamic — AED 15,444.42 / 16,500 (94% — near limit)
- Mashreq noon VIP — AED 4,218.04 / 5,500

**8 active EMIs**
- CBD Cash on Call (8/24) — 627/mo
- ENBD LOC (22/24) — 739/mo — **ends Aug 2026** 🎉
- ENBD Min of Interior (9/12) — 158/mo — **ends Sep 2026** 🎉
- EI Motor Bay (10/12) — 138/mo — ends Aug
- EI Safari (10/12) — 87/mo — ends Aug
- EI Min of Interior (2/9) — 154/mo
- EI Scholars School (4/12) — 137/mo
- Mashreq RBT (0/6) — 118/mo — **NEW** (started Jun)

**6 recurring bills**
- DU Quick Pay (Mashreq) — 167/mo
- FEWA Federal Electricity (Mashreq) — 194/mo
- E& Digital (ENBD) — ~46/mo
- Tabby BNPL big (EI) — 68/mo
- Tabby BNPL small (EI) — 39/mo
- FEWA (EI variant) — 206/mo

**Categories with budgets** (from your estimates)
- Supermarket — AED 1,500
- Food/Dining — AED 300
- Petrol/Travel — AED 200
- Utilities — AED 1,000
- School — AED 2,000
- Health/Medical — AED 200
- Visa/Govt — AED 100
- Online Shopping — AED 200
- BNPL — AED 150
- Auto, Home, Personal Care, Family — smaller buckets

---

## Backing up your data

- **Settings → Download backup** → save JSON to Google Drive / email yourself
- If you ever reinstall or switch phones: **Settings → Import backup**

---

## What the app shows you (key numbers updated for Jun)

**Cashflow snapshot if you stop overspending:**
- Income: 11,550
- − Rent: 1,700
- − Card min payments: 3,417
- − Recurring bills (some inside mins): ~720
- = **Free cash: ~6,400**

But your June actual spending categories show:
- Supermarket: 1,938 (130% of budget)
- Food/Dining: **997 (332% of 300 budget — major leak)**
- Petrol: **831 (416% of 200 budget — major leak)**
- Visa/Govt: 2,798 (one-time visa renewal)

Use the app's category bars to see this in real time as you log purchases.

---

## Troubleshooting

**App didn't update** — service worker cached the old version. In Chrome, long-press the app → App info → Storage → Clear cache. Then reopen.

**Can't install** — only works on https URL (GitHub Pages or Netlify), not local file:// paths.

**Notifications don't fire** — they only fire when the app is open or was recently used. Open it daily.

**Wife and you don't share data** — by design (no backend). Use Export/Import backup for weekly sync.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app |
| `manifest.json` | Install metadata |
| `sw.js` | Offline support |
| `icon-192.png` / `icon-512.png` / `apple-touch-icon.png` | App icons |
| `INSTALL.md` | This guide |
