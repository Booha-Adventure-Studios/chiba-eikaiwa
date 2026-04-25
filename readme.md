
# 千葉英会話ガイド / Chiba Eikaiwa Guide

A neutral, flat directory of English conversation schools across Chiba Prefecture.

**Live:** https://chiba-eikaiwa.github.io

---

## How it works

Every school is stored as a data object in `schools.js`. The site is a pure HTML/CSS/JS engine — add a school to `schools.js`, it appears everywhere: the hero slideshow, the city section, the card. No CMS, no build step, no dependencies.

---

## Adding a school

Open `schools.js` and add an entry to the `SCHOOLS` array:

```js
{
  id: "my-school",              // unique slug, no spaces
  name: "スクール名",             // Japanese name
  nameEn: "School Name",        // English name
  city: "成田市",                 // Japanese city name
  cityEn: "Narita",             // English city name
  logo: "img/my-school.png",    // path to logo image, or null
  logoInitials: "NS",           // shown if no logo
  logoColor: "#2a5a8a",         // background color for logo box
  logoTextColor: "#ffffff",     // text color for initials
  ages: ["子ども", "大人"],        // Japanese age group labels
  agesEn: ["Kids", "Adults"],   // English age group labels
  prices: [
    { label: "体験 / Trial", amount: "¥500" },
    { label: "月謝 / Monthly", amount: "¥8,000〜" }
  ],
  points: [                     // Japanese bullet points (3-4)
    "少人数制で発話機会が多い",
    "ネイティブ教師による指導",
    "英検対策コースあり",
    "駅から徒歩3分の好立地"
  ],
  pointsEn: [                   // English bullet points (3-4)
    "Small classes, more speaking time",
    "Taught by native English teacher",
    "Eiken exam prep available",
    "3-minute walk from the station"
  ],
  website: "https://your-school-website.com"
}
```

Save the file. Done.

---

## File structure

```
index.html     ← The full site (engine + layout)
schools.js     ← All school data (the only file you edit)
img/           ← School logos (optional — initials shown if missing)
README.md      ← This file
```

---

## Deploy to GitHub Pages

1. Create a new GitHub repo named `chiba-eikaiwa`
2. Upload `index.html`, `schools.js`, `README.md` (and `img/` folder if using logos)
3. Go to **Settings → Pages → Source: Deploy from branch → main → / (root)**
4. Site goes live at `https://chiba-eikaiwa.github.io`

---

## Design principles

- Every school card is identical in structure — no school gets more or less space
- No rankings, no star ratings, no "top" labels
- Bilingual throughout — Japanese first, English toggle on each card
- Hero slideshow order is randomised on every page load
- Schools are grouped by city, listed in the order they appear in `schools.js`
