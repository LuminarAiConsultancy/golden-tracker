# Town of Golden — Council Priorities & Resolution Tracker

A public dashboard that tracks the Town's progress on Council's 2025–2028 Strategic
Priorities and the status of adopted Council resolutions. Departments (not named
staff) own each item. The public sees a read-only view; authorized staff sign in to
update it.

**No AI is used.** This is a standard, database-backable web page.

---

## 🔗 What's the live demo?

The file **`index.html`** at the top of this repo IS the complete dashboard — one
self-contained file (all code, fonts and logo embedded). Hosting it gives you a
working, clickable demo.

> ⚠️ **Demo vs. real:** In this hosted demo, staff editing works **in your own
> browser only**, and the "Staff sign in" uses a placeholder password
> (`golden2026`). It's perfect for showing *how it works* — but edits are not yet
> shared or saved for everyone. Making editing real is "Stage 2" (see the guides).

---

## 🚀 Put the demo online (pick one — both are free)

### Option A — Netlify (fastest)
1. Go to **app.netlify.com/drop**
2. Drag this whole folder (or just `index.html`) onto the page
3. You instantly get a public link like `https://golden-tracker.netlify.app`
4. (Optional) Make a free Netlify account to keep the link permanent and rename it

### Option B — GitHub Pages
1. Create a **public** repository and upload these files
2. Go to **Settings → Pages**
3. Set **Source** to your `main` branch, root folder
4. Wait ~1 minute → it gives you a live link like
   `https://YOURNAME.github.io/golden-tracker/`

Both automatically serve `index.html`, so the demo "just works" with no configuration.

---

## 📁 What's in this repo

| Path | What it is | For |
|---|---|---|
| `index.html` | The complete dashboard, one self-contained file. **This is the demo.** | Everyone |
| `docs/START HERE — Setup & IT Guide.html` | Master guide: install, hosting, IT requirements, checklist, costs | IT / manager |
| `docs/Implementation Brief.html` | Plain-language overview of login, hosting & compliance | Manager / IT |
| `docs/Developer Handoff Note.html` | Data model + where to connect a back end | Developer |
| `docs/Integration Map.html` | The 4 backend connection points, mapped to API endpoints | Developer |
| `source/` | The editable code. All content lives in `source/app/data.js` | Developer |

*(Open the `docs/*.html` files in a browser; each has a "Print / Save as PDF" button.)*

---

## 🧭 The two stages

**Stage 1 — Public view (this demo):** works now. Host `index.html` and the public /
Council can see progress. To change content, edit `source/app/data.js` and re-publish.

**Stage 2 — Live staff editing (a developer build):** add three pieces so edits are
shared and permanent —
1. **Database** (e.g. AWS DynamoDB/RDS, or Supabase/Firebase)
2. **Real staff login** (ideally Microsoft Entra ID, so staff use their `@golden.ca`
   accounts)
3. **A small API/service** connecting them

Permissions are already built into the UI: public = view only; a department director
edits only their items; **CAO & Administrator** edit everything and reassign
departments. See `docs/Developer Handoff Note.html` for the data model.

---

## ✅ Compliance reminders (BC municipality)
- Store data **in Canada** (FOIPPA) — e.g. AWS `ca-central-1` (Montréal)
- Keep an **edit/audit log** — progress notes are public records
- Public page should meet **WCAG 2.1 AA**

---

*Town of Golden · Council Priorities & Resolution Tracker*
