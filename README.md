# ⚗️ Element Craft Town

**English** | [简体中文](./README.zh-CN.md)

A cozy alchemy-and-city-building game that runs entirely in **one zero-dependency HTML file** — no framework, no build step, no server. Just open `index.html` and play.

## Gameplay

- 🎰 **Lucky Draw Start** — draw your initial elements (Earth/Water/Fire/Air, 10–99 each) plus a handful of starter coins
- ⚗️ **Tap or Drag Alchemy** — tap an element to auto-fill the next slot, or drag to a specific slot. Combine two elements to discover 20+ recipes (Earth+Water=Mud, Mud+Fire=Brick…). Crafting is free! **Batch crafting** unlocks as you progress: assets >100 → 1–5 at once, >1000 → 1–20, >10000 → 1–100
- 🏗️ **Build Your Town** — gather materials to construct huts, shops, gardens, manors (generate coins) and a town hall (global +10% production bonus, no direct income). **Treasure Chests (🧰)** are required as building materials for high-tier structures like Manors and City Hall
- 🗺️ **Town Map** — unlocked after building a Hut + Shop; visual map with 5 regions (Plain / Hillside / Forest / Riverside / Downtown), each with cost & output multipliers. Includes a stats bar (total buildings / coin output / developed regions), building badges, and a per-region building grid
- 🧬 **The Hidden Life Line** — Energy + high-tier "dead-end" elements = 🧬 Life, whose tier depends on the recipe; hatch pets from it. **Max-tier Life has a 1/100 chance to hatch the legendary 🐼 Panda**
- 🐾 **Pet Raising** — name your pets (up to 15 chars, English names in EN mode), track birth time (minutes→hours→days), raise intimacy (0–100, +0.5% bonus per level, unlocks custom avatar at Lv.10), per-species diets, hunger & HP per pet, a pet hospital (pets get sick but never die), and town-wide production bonuses from +1% to +5% base + intimacy bonus. Grid card layout with inline feed/play/heal actions
- 🛒 **Element Shop** — buy common elements (tier ≤3) with coins; price = tier × 5. **Batch buying** with the same tiered limits as crafting
- 🧙‍♂️ **Tab-Aware Elder NPC** — the elder gives context-specific hints per tab: smart recipe recommendations in Craft, building tips in Town, shop rules in Shop, and actual pet bonus breakdowns in Pet (including intimacy math: every 10 intimacy = 1 level = +0.5%). Tap the elder to dismiss early. Auto-hints on tab switch

## Features

- Single HTML file, fully static — deploy to GitHub Pages / Cloudflare Pages
- 🌐 **Bilingual (中文 / English)** — toggle anytime in header or on the intro screen; element names, building names, NPC dialogue, settings, and all UI text fully localized
- Auto-save in localStorage; offline income capped at 1 hour
- 📦 Save snapshots — JSON export/import with versioned migration (v3); choose **full export** (with custom pet avatars) or **lightweight export** (no avatars, smaller file). Import auto-detects older save versions and migrates
- 🎨 4 built-in themes with AI-generated background art (Night / Forest / Sand / Snow), plus a 5th **Custom** slot — upload any image and it becomes your game background
- 🖼️ Custom background upload — pick any image, auto-compressed to ≤1920px, stored in IndexedDB (no save-file bloat)
- 🖼️ Custom asset packs — upload `theme.json` to replace pet/element/region art (stored in IndexedDB, auto-resized, falls back to built-in cartoon art then emoji)
- 🐾 6 built-in cartoon pet portraits with idle bounce animation; custom avatar upload unlocked at intimacy Lv.10
- 📱 Mobile-first responsive layout — compact two-row header (avoids container UI overlap), natural page scrolling, all elements fully visible without internal scroll areas
- 📕 **Xiaohongshu (Little Red Book) mini-app build** — a separate distribution optimized for the XHS in-app browser: no JSON import/export, no `window.prompt` (custom modal instead), no inline `onclick`, safe-area padding for XHS header buttons. Located in `Desktop/synth-town-minitool/`

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

**GitHub Pages:** repo Settings → Pages → select the `main` branch.

**Cloudflare Pages:** connect the repo, build command left empty, output directory `/`.

**Xiaohongshu mini-app:** use the pre-packaged `synth-town-xiaohongshu.zip` (generated from `Desktop/synth-town-minitool/`). This build removes JSON import/export and `window.prompt` to comply with XHS container restrictions.

## Save Version History

| Version | Changes | Migration |
|---------|---------|-----------|
| v1 | Initial release (elements, buildings, basic pets as counters) | — |
| v2 | Plot/land system (5 regions, purchasable lots, building placement) | Old `regions` counter → `plots` array; `null`→`false` repair for serialization bug |
| v3 | Pet enhancement (named pets, birth timestamp, intimacy system, custom avatars, pet instances with HP/hunger/sickness) | Pet counters → pet instances; new fields defaulted via `migratePetFields()` |

Export includes `version: SAVE_VERSION` and `exportedAt` timestamp. Import checks `data.version < SAVE_VERSION` and auto-migrates.

## License

[MIT](./LICENSE) © Nicky
