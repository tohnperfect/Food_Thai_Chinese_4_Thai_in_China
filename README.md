# Thai → Chinese Food Dictionary 🍜
## พจนานุกรมอาหารไทย–จีน · 泰中美食词典

> **Thai–Chinese food name discovery for Thai travelers visiting China without knowing Chinese.**
>
> Type a dish in Thai → get the Chinese characters → paste into Meituan / Dianping / WeChat / any Chinese app.

[**🔗 Live demo**](https://tohnperfect.github.io/Food_Thai_Chinese_4_Thai_in_China/)

---

## Why this exists

If you've ever travelled to China without reading Chinese, ordering food is the hardest part of the day. Apps like **美团 (Meituan)**, **大众点评 (Dianping)**, **饿了么 (Ele.me)**, and even restaurant QR-code menus expect you to type or select Chinese characters. Google Translate works, but you lose the dish name's local meaning and often translate it back to something nobody serves.

This tool solves one specific problem: you know the **Thai name** of the food you want — you just need the **Chinese characters** to paste into an app.

Search **"ติ่มซำ"** → tap → 点心 is in your clipboard. Done.

---

## Features

- **872 dishes** across 21 categories (Chinese regional, Thai, Japanese, Korean, Vietnamese, Indian, Malaysian, Indonesian, Singaporean)
- **Fuzzy Thai search** — tolerates tone marks, vowel diacritics, common transliteration variants, and typos
- **Multi-language input** — search in Thai (ผัดไทย), English (pad thai), or pinyin (chao mian, with or without tone marks)
- **One-tap copy** of Chinese characters to clipboard (with fallback for older browsers)
- **Usage stats** — sees which dishes you actually copy and which you keep looking up; runs entirely in your browser, never sent anywhere
- **Mobile-first design** — works perfectly on a phone while you're standing outside a 麻辣烫 stall
- **Zero dependencies** — pure HTML/CSS/JS, no build step, no framework, no server
- **Offline-capable** — once loaded, works without internet (fonts cached after first visit)

---

## Categories (872 dishes)

| | Category | Thai | Chinese | Count |
|---|---|---|---|---|
| 🥟 | Dim Sum | ติ่มซำ | 点心 | 39 |
| 🍜 | Noodles | ก๋วยเตี๋ยว | 面 | 47 |
| 🍚 | Rice | ข้าว | 饭 | 40 |
| 🌶️ | Sichuan | เสฉวน | 川 | 23 |
| 🦆 | Cantonese | กวางตุ้ง | 粤 | 22 |
| 🥢 | Northern Chinese | ภาคเหนือจีน | 京 | 18 |
| 🦀 | Shanghai / Jiangsu | เซี่ยงไฮ้ | 沪 | 12 |
| 🥣 | Tonic / Banquet | เครื่องตุ๋น/บำรุง | 滋补 | 46 |
| 🥩 | Meat | เนื้อสัตว์ | 肉 | 52 |
| 🦐 | Seafood | ทะเล | 海鲜 | 48 |
| 🥬 | Vegetables | ผัก | 蔬 | 59 |
| 🍲 | Soup / Hotpot | ซุป/หม้อไฟ | 汤 | 31 |
| 🍢 | Snacks | ของกินเล่น | 小吃 | 39 |
| 🍰 | Desserts | ของหวาน | 甜 | 32 |
| 🥤 | Drinks | เครื่องดื่ม | 饮 | 68 |
| 🍎 | Fruits | ผลไม้ | 果 | 36 |
| 🧂 | Ingredients & Seasonings | วัตถุดิบ | 食材 | 73 |
| 🇹🇭 | Thai dishes → Chinese | ไทย→จีน | 泰 | 69 |
| 🇯🇵 | Japanese | ญี่ปุ่น | 日 | 52 |
| 🇰🇷 | Korean | เกาหลี | 韓 | 35 |
| 🌏 | Other Asian | อื่นๆ | 其他 | 31 |

---

## How to use

1. **Open the page** on your phone
2. **Type a Thai dish name** (or English / pinyin) into the search box
3. **Tap the copy button** on the result card — Chinese characters go to your clipboard
4. **Switch to Meituan / Dianping / WeChat** and paste

### Search examples that work

| You type | What it finds |
|---|---|
| `ติ่มซำ` | 点心 (and all dim sum variants) |
| `dim sum` | same |
| `xiaolongbao` | 小笼包 |
| `XLB` | 小笼包 |
| `เปกิงดัก` (misspelled) | 北京烤鸭 (Peking duck) |
| `mala` | 麻辣烫, 麻辣香锅, 麻辣鸭脖, etc. |
| `หม่าล่า` | same |
| `ทุเรียน` | 榴莲 |
| `บะหมี่หลานโจว` | 兰州拉面 |
| `กระเพาะปลา` | 鱼肚羹 (and 4 other variants) |
| `หม้อไฟ` | all hotpot family — 火锅, 泰式火锅 (สุกี้), 涮锅 (ชาบู), 寿喜烧 (sukiyaki), 涮羊肉, etc. |
| `สุกี้` | same hotpot family, with Thai suki entries ranked first |
| `บะหมี่` | all noodle family — 拉面 (ราเมง), 乌冬面 (อุด้ง), 越南河粉 (เฝอ), 担担面, 刀削面, etc. |
| `ราเมง` | same noodle family, with ramen variants ranked first |

### Search tolerance

The Thai matcher normalises tone marks (`่ ้ ๊ ๋`) and vowel diacritics, so `ผัดไท` and `ผัดไทย` both match. Pinyin matching ignores tone marks, so `ma la` finds `má là`. There's also a Levenshtein-distance fallback for genuine typos, with a relevance score that ranks exact matches above fuzzy ones.

**Family tags** group related dishes so a query for one surfaces all of them. Direct name matches always rank above family matches, so you get the closest hit first and the rest of the family below. Current families:

- **`hotpot`** (24 dishes) — Thai สุกี้, ชาบู, หม้อไฟ, Sichuan 火锅, Mongolian 涮羊肉, Japanese 寿喜烧 / 涮涮锅, Korean 部队锅 / 泡菜火锅, etc. Triggers: `หม้อไฟ`, `สุกี้`, `ชาบู`, `hotpot`, `shabu`, `suki`, `sukiyaki`, `火锅`.
- **`noodle`** (71 dishes) — Thai ก๋วยเตี๋ยว / บะหมี่ / ราเมง / เฝอ / อุด้ง / โซบะ, Chinese 拉面 / 米粉 / 米线 / 河粉 / 担担面 / 刀削面, Vietnamese 越南河粉, Korean 炸酱面, etc. Triggers: `ก๋วยเตี๋ยว`, `บะหมี่`, `ราเมง`, `อุด้ง`, `โซบะ`, `เฝอ`, `มาม่า`, `noodle`, `ramen`, `udon`, `soba`, `pho`, `拉面`, `米粉`, `米线`, `面条`.

---

## Usage Stats

Tap the **สถิติ (Stats)** button in the top-right to see:

- **Most Copied** — dishes you actually used (these are the most useful entries for you)
- **Most Viewed** — dishes that appeared most often in your search results
- **Summary** — total copies, unique dishes, total searches, days since first use
- **Export JSON** — download your stats with full dish info (Thai/pinyin/English/category) for analysis
- **Reset** — wipe stats and start fresh

All data lives in your browser's `localStorage`. **Nothing is sent to any server.** Open the page in a different browser or incognito window and you'll see a fresh empty state.

---

## Deploy your own copy (GitHub Pages)

```bash
# 1. Clone or fork
git clone https://github.com/tohnperfect/thai-chinese-food-dict.git
cd thai-chinese-food-dict

# 2. (Optional) edit food_dict.html to add/change dishes

# 3. Push to GitHub
git push origin main
```

Then on GitHub:

1. Go to **Settings → Pages**
2. **Source:** Deploy from a branch
3. **Branch:** `main` / `/ (root)`
4. Save. Wait ~1 minute.
5. Visit `https://<your-username>.github.io/thai-chinese-food-dict/`

If `food_dict.html` is your only file, you might want to rename it to `index.html` so the root URL works without specifying the filename:

```bash
mv food_dict.html index.html
git commit -am "rename for GH Pages root"
git push
```

---

## Tech stack

| | |
|---|---|
| Framework | none |
| Build step | none |
| Dependencies | Google Fonts (Fraunces, DM Sans, IBM Plex Sans Thai, Noto Serif TC) |
| Storage | `localStorage` for usage stats |
| Clipboard | `navigator.clipboard.writeText` with `execCommand('copy')` fallback |
| Search | Custom scorer combining exact / startsWith / includes / Levenshtein ratio |
| Footprint | ~150 KB total (HTML + inlined CSS + JS + 872-entry dataset) |
| Browser support | Any modern mobile or desktop browser (iOS Safari 14+, Chrome 80+) |

---

## Data model

Each dish in `DATA` follows this shape:

```js
{
  thai: "ติ่มซำ",                   // primary Thai name
  alt:  ["ดิมซำ", "dim sum"],       // alternate spellings, English, transliterations
  cn:   "点心",                     // Chinese characters (what gets copied)
  py:   "diǎn xīn",                 // pinyin with tone marks
  en:   "dim sum",                  // English gloss
  tags: ["hotpot"],                 // optional — family tags (see FAMILIES)
  cat:  "dimsum"                    // category id (see CATS array)
}
```

**Search weights** (from `scoreItem`):

- Thai exact / startsWith / includes: weight 1.0
- Alt spellings: 0.92
- English / pinyin / stripped-pinyin: 0.78
- Chinese: 1.0
- Family-tag keywords (from `FAMILIES`): 0.55 — surfaces related dishes when the user searches a family term, but always ranks below direct name matches

A Levenshtein-ratio fallback fires when no substring match is found, scoring `ratio × 65` for ratios above 0.55.

---

## Contributing

Found a missing dish, wrong character, or weird transliteration? Open an [issue](https://github.com/tohnperfect/thai-chinese-food-dict/issues) or PR.

When adding a dish:

1. Double-check the Chinese characters against a real source (Wikipedia ZH, Dianping, Meituan menu screenshots)
2. Use pinyin with tone marks (`á à ǎ ā ā` etc.) — these are searchable both with and without tones
3. Add 1–3 alt spellings if the dish has common Thai romanisations or English names
4. Pick the right category — when in doubt, choose the most specific one

---

## Roadmap ideas

- [ ] PWA manifest + offline-first service worker (true installable app)
- [ ] Dark mode
- [ ] Save favorites locally
- [ ] Voice input (Thai speech → Chinese characters)
- [ ] Camera OCR for printed Chinese menus → translate back to Thai
- [ ] Restaurant phrase pack (ขอช้อนเพิ่ม / 请加一双勺子, ไม่เผ็ด / 不要辣, etc.)
- [ ] Aggregated anonymous stats from contributors (opt-in)

---

## Privacy

- **No analytics.** No Google Analytics, no Cloudflare, no Plausible — nothing.
- **No backend.** The page is a static HTML file; there is no server to talk to.
- **Stats are local.** Your `localStorage` usage data never leaves your device.
- **Fonts** are loaded from `fonts.googleapis.com` (Google). If this concerns you, fork and self-host the fonts.

---

## License

MIT — do whatever you want with it. Attribution appreciated but not required.

---

## Credits

Built for Thai travelers in China who'd rather eat well than fight with Google Translate.

- Maintained by [@tohnperfect](https://github.com/tohnperfect)
- Curated against menus from Beijing, Shanghai, Chengdu, Guangzhou, Hong Kong, and conversations with Chinese colleagues

If this helped you order something delicious in China, a ⭐ on the repo is the nicest thank-you. 谢谢 · ขอบคุณครับ
