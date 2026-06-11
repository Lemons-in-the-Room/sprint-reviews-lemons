# Sprint Bubbles

Interactive sprint visualization for Lemo and Lemo Junior.
Embedded in Notion via GitHub Pages.

---

## Setup (one time, ~10 minutes)

### 1. Create a GitHub repo

Go to github.com → New repository → name it `sprint-bubbles` → Public → Create.

### 2. Upload these two files

In the repo, click "Add file" → "Upload files" → drag in:
- `index.html`
- `data.json`

Commit directly to main.

### 3. Enable GitHub Pages

Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: `main` → folder: `/ (root)` → Save.

Wait ~60 seconds. Your URL will be:
```
https://YOUR-USERNAME.github.io/sprint-bubbles/
```

Test it in your browser — you should see the bubble chart.

### 4. Embed in Notion

In any Notion page, type `/embed` → paste the GitHub Pages URL → Embed link.

Resize the embed block to taste (drag the bottom edge). Recommended height: 800px+.

---

## Updating every 2 weeks (5 minutes)

Open `data.json` on GitHub.com → click the pencil icon (Edit) → scroll to the bottom of the file → add a new sprint object before the final `]`.

Copy the template below, fill in the real data, paste it after the last sprint (add a comma after the previous sprint's closing `}`):

```json
{
  "id": 11,
  "label": "Sprint 11",
  "dates": "Jun 23–Jul 4",
  "version_lemo": "Lemo v0.5.1",
  "version_lj": "LJ v1.1",
  "lemo": {
    "dev": [
      { "key": "LEM-550", "title": "Your task title here", "who": "Lazar" }
    ],
    "art": [
      { "key": "LEM-551", "title": "Your task title here", "who": "Elisa" }
    ],
    "sound": [
      { "key": null, "title": "Your task title here", "who": "Elan" }
    ],
    "vfx": []
  },
  "lj": {
    "dev": [
      { "key": "LJ-200", "title": "Your task title here", "who": "Chiara" }
    ],
    "art": [],
    "sound": [],
    "vfx": []
  }
}
```

Click "Commit changes" → the site updates in ~60 seconds → Notion embed refreshes on next page load.

### Rules

- `"key"` can be a Jira key like `"LEM-550"` or `null` if there's no ticket yet
- `"who"` must be one of: `Lazar`, `Chiara`, `Elisa`, `Federico`, `Elan`, `Manuel`
- Empty departments use `[]`
- `"vfx"` is only used when Federico has VFX-specific work

---

## File structure

```
index.html   — the widget (never needs editing)
data.json    — all sprint data (edit this every 2 weeks)
README.md    — this file
```

---

## Adding a new team member

Open `index.html` → find the `WHO` object near the top → add a line:

```js
NewName: { bg: '#hexcolor', color: '#darkerhex' },
```

Pick any light bg color and a darker version of the same hue for the text.
