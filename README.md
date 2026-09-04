# ⚗️ Element Craft Town

**English** | [简体中文](./README.zh-CN.md)

A cozy alchemy-and-city-building game that runs entirely in **one zero-dependency HTML file** — no framework, no build step, no server. Just open `index.html` and play.

## Gameplay

- 🎰 **Lucky Draw Start** — draw your initial elements (Earth/Water/Fire/Air, 10–99 each) plus a handful of starter coins
- ⚗️ **Tap or Drag Alchemy** — tap an element to auto-fill the next slot, or drag to a specific slot. Combine two/three elements to discover **30+ recipes** (Earth+Water=Mud, Mud+Fire=Brick…). Crafting is free! **Batch crafting** unlocks by **net worth** (coins + chests×10 + elements tier×5 + pets by HP×5 + buildings & land at full value): net worth >100 → 1–5 at once, >1000 → 1–10, >5000 → 1–50, >10000 → 1–100, ≥1,000,000 → no cap. Numeric inputs include −/＋ steppers and reset to 1 after each craft/purchase. The **element library** shows all **36** discoverable cards (basics + advanced + Life HP variants + Elixirs + Legendary) and the discovery progress `X/36` matches the grid exactly
- 📕 **Recipe Book** — a password-locked grimoire listing every formula by element tier. Enter `1986` to reveal all recipes up to tier 3; enter `cosmos` to unlock the rest. Life recipes are shown at their real tier (e.g. Energy+Brick = HP 5) with an `(HP xx)` tag; the 🔩Metal+🔩Metal **Treasure Chest** recipe appears under tier 8. Unlock progress is stored independently of saves (survives export/import and reset)
- 🏗️ **Build Your Town** — gather materials to construct huts, shops, gardens, manors, factories (generate coins) and a town hall (global +10% production bonus, no direct income). **Treasure Chests (🧰, crafted from 🔩Metal+🔩Metal)** are required as building materials for high-tier structures like Manors and City Hall. **Building cost = element bundle (fixed at the countryside standard for every region) + build coins (base × region cost multiplier) + plot price (region-scaled)**. City Hall max 2 (2nd ×1.5); Factory only in the Factory District
- 🗺️ **Town Map** — unlocked after building any 2 buildings; visual map with **6 regions** (Countryside / Hillside / Forest / Riverside / Downtown / Factory), each with its own cost & output multipliers, plot price and building capacity (Downtown 8 plots, Factory 5). Includes a stats bar (total buildings / coin output / developed regions), building badges, and per-region building grid. Free layout mode unlocked by the 🏆 Real Estate Tycoon badge
- 🛒 **Element Shop** — tabbed sections (Basic / Advanced / Life / Legendary): **Basic & Legendary are always purchasable**, Advanced unlocks once you craft any advanced element, Life unlocks once you craft any Life variant. Batch buying uses the same tiered limits as crafting. **Bundle bar** (one-tap full material packs, unlocked by the Element Master badge; buy up to 5, City Hall 1) and a **Trade-in shop** (sell Lv.4+ elements & pets at 80% buy price)
- 🧬 **The Hidden Life Line** — Energy + high-tier "dead-end" elements = 🧬 Life. **Life is split by real HP (5 / 6 / 9 / 10 / 11)** — each HP variant counts separately in the library and discovery progress (e.g. Energy+Brick → HP 5, Energy+Bunch → HP 10). Hatch pets from it. **Max-tier Life has a 1/100 chance to hatch the legendary 🐼 Panda**
- 🐾 **Pet Raising** — name your pets (up to 15 chars, English names in EN mode), track birth time (minutes→hours→days), raise intimacy (0–100, +0.5% bonus per level, unlocks custom avatar at Lv.10), per-species diets, hunger & HP per pet, a pet hospital (pets get sick but never die), and town-wide production bonuses from +1% to +5% base + intimacy bonus. Grid card layout with inline feed/play/heal actions
- 🏆 **Achievements & Badges** — Element Master (collect all elements, unlocks the bundle bar), Real Estate Tycoon (own all plots with buildings, unlocks free layout), Animal King (own every pet species), 万元户 / Millionaire (net worth milestones) — each with a badge gallery, celebration overlay, and downloadable badge images
- 🎠 **Pet Playpark** — unlocked once you own a 🐼 Panda; place all 10 pets in themed species nests, drag to swap, and save/share the scene as an image
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
