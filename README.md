# ⚗️ Element Craft Town

**English** | [简体中文](./README.zh-CN.md)

A cozy alchemy-and-city-building game that runs entirely in **one zero-dependency HTML file** — no framework, no build step, no server. Just open `index.html` and play.

## Gameplay

- 🎰 **Lucky Draw Start** — draw your initial elements (Earth/Water/Fire/Air, 10–99 each) plus a handful of starter coins
- ⚗️ **Tap or Drag Alchemy** — tap an element to auto-fill the next slot, or drag to a specific slot. Combine two elements to discover 20+ recipes (Earth+Water=Mud, Mud+Fire=Brick…). Crafting is free!
- 🏗️ **Build Your Town** — gather materials to construct huts, shops, gardens, manors (generate coins) and a town hall (global +10% production bonus, no direct income)
- 🗺️ **Town Map** — unlocked after building a Hut + Shop; visual map with 5 regions (Plain / Hillside / Forest / Riverside / Downtown), each with cost & output multipliers. Includes a stats bar (total buildings / coin output / developed regions), building badges, and a per-region building grid
- 🧬 **The Hidden Life Line** — Energy + high-tier "dead-end" elements = 🧬 Life, whose tier depends on the recipe; hatch pets from it. **Max-tier Life has a 1/100 chance to hatch the legendary 🐼 Panda**
- 🐾 **Pet Raising** — name your pets (up to 15 chars), track birth time (minutes→hours→days), raise intimacy (0–100, +0.5% bonus per level, unlocks custom avatar at Lv.10), per-species diets, hunger & HP per pet, a pet hospital (pets get sick but never die), and town-wide production bonuses from +1% to +5% base + intimacy bonus
- 🧙‍♂️ **Tab-Aware Elder NPC** — the elder gives context-specific hints per tab: smart recipe recommendations in Craft, building tips in Town, shop rules in Shop, and actual pet bonus breakdowns in Pet. Auto-hints on tab switch

## Features

- Single HTML file, fully static — deploy to GitHub Pages / Cloudflare Pages
- Auto-save in localStorage; offline income capped at 1 hour
- 📦 Save snapshots — JSON export/import with versioned migration (v3); choose **full export** (with custom pet avatars) or **lightweight export** (no avatars, smaller file)
- 🎨 4 built-in themes with AI-generated background art (Night / Forest / Sand / Snow), plus a 5th **Custom** slot — upload any image and it becomes your game background
- 🖼️ Custom background upload — pick any image, auto-compressed to ≤1920px, stored in IndexedDB (no save-file bloat)
- 🖼️ Custom asset packs — upload `theme.json` to replace pet/element/region art (stored in IndexedDB, auto-resized, falls back to built-in cartoon art then emoji)
- 🐾 6 built-in cartoon pet portraits with idle bounce animation; custom avatar upload unlocked at intimacy Lv.10
- 📱 Mobile-first responsive layout — compact two-row header (avoids container UI overlap), natural page scrolling, all elements fully visible without internal scroll areas

## Custom Asset Pack Format

```json
{
  "pets":     { "cat": "data:image/png;base64,..." },
  "elements": { "brick": "data:image/png;base64,..." },
  "regions":  { "river": "data:image/png;base64,..." }
}
```

Specs: pets/elements 128×128, regions 512×256, ≤200KB each (oversized images are automatically resampled).

## Deploy

GitHub Pages: repo Settings → Pages → select the `main` branch.

## License

[MIT](./LICENSE) © Nicky
