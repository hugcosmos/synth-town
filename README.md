# ⚗️ 元素合成小镇 / Element Craft Town

> **English** | [中文](#中文说明)

A cozy alchemy-and-city-building game that runs entirely in **one zero-dependency HTML file** — no framework, no build step, no server. Just open `index.html` and play.

## Gameplay

- 🎰 **Lucky Draw Start** — draw your initial elements (Earth/Water/Fire/Air, 10–99 each) plus a handful of starter coins
- ⚗️ **Drag & Drop Alchemy** — combine two elements to discover 20+ recipes (Earth+Water=Mud, Mud+Fire=Brick…). Crafting is free!
- 🏗️ **Build Your Town** — gather materials to construct huts, shops, gardens, manors and a town hall that generate coins
- 🗺️ **Town Map Mode** — unlocked after building a Hut + Shop; 5 regions (Plain / Hillside / Forest / Riverside / Downtown), each with its own cost & output multipliers
- 🧬 **The Hidden Life Line** — Energy + high-tier "dead-end" elements = 🧬 Life, whose tier depends on the recipe; hatch pets from it. **Max-tier Life has a 1/100 chance to hatch the legendary 🐼 Panda**
- 🐾 **Pet Raising** — per-species diets, hunger & HP per pet, a pet hospital (pets get sick but never die), and town-wide production bonuses from +1% to +5%
- 🧙‍♂️ **Summon the Elder** — stuck? Get a random hint for a craftable recipe you haven't discovered yet

## Features

- Single HTML file, fully static — deploy to GitHub Pages / Cloudflare Pages
- Auto-save in localStorage; offline income capped at 1 hour
- 📦 Save snapshots — JSON export/import for multiple playthroughs
- 🎨 4 built-in color themes (Night / Forest / Sand / Snow) with pure-CSS patterned backgrounds
- 🖼️ Custom asset packs — upload `theme.json` to replace pet/element/region art (stored in IndexedDB, auto-resized, falls back to emoji)
- Full touch support (Pointer Events) — plays great on mobile

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

---

# 中文说明

一个单文件、零依赖的浏览器合成经营小游戏。双击 `index.html` 即可游玩，无需安装任何东西。

## 玩法

- 🎰 **开局幸运抽取**：抽取四大基础元素（土/水/火/气，各 10~99 个）+ 少量启动金币
- ⚗️ **拖拽合成**：把两个元素拖到合成台组合出新元素（土+水=泥、泥+火=砖……），合成免费，20+ 条配方
- 🏗️ **建造小镇**：攒够建材建造小屋、商铺、花园、豪宅、市政厅，持续产出金币
- 🗺️ **底图模式**：建成小屋+商铺后解锁，5 大分区（平原/山脚/林间/河岸/市中心）各有成本/产出系数
- 🧬 **生命线（隐藏玩法）**：⚡能量 + 高级"死路元素" = 🧬生命，生命值由材料层级决定；孕育宠物（猫/兔/狗/牛/马），**满级生命 1/100 出 🐼熊猫**
- 🐾 **宠物养成**：分物种口粮、饱食度/生命值、宠物医院（生病不死可治疗）、物种产出加成 +1%~+5%
- 🧙‍♂️ **召唤长老**：卡住时随机提示一条"原料已齐"的隐藏配方

## 特性

- 单 HTML 文件，纯静态，可部署到任意静态托管（GitHub Pages / Cloudflare Pages）
- localStorage 自动存档，离线收益封顶 1 小时
- 📦 存档副本：JSON 导出/导入，多副本切换
- 🎨 4 套配色主题（紫夜/森绿/暖沙/雪境），纯 CSS 花纹背景
- 🖼️ 自定义素材包：`theme.json` 导入宠物/元素/地块贴图，存 IndexedDB，自动压缩，回落 emoji
- 手机触屏全兼容（Pointer Events）

## 自定义素材包格式

```json
{
  "pets":     { "cat": "data:image/png;base64,..." },
  "elements": { "brick": "data:image/png;base64,..." },
  "regions":  { "river": "data:image/png;base64,..." }
}
```

规格：宠物/元素 128×128、地块 512×256、单张 ≤200KB（超规格自动重采样压缩）。

## 部署

GitHub Pages：仓库 Settings → Pages → 选择 `main` 分支即可。

## License

[MIT](./LICENSE) © Nicky
