# Changelog

## v1.2 — March 31, 2026

### UI Overhaul (credit: Frank / frankyy — GitHub Issue #1)
- **3-column preset grid** — presets on all four stat tabs reorganized into labeled columns: 🟢 T3 Meta / 🩷 Zero Stat / 🔴 Cap Thresholds. Much easier to scan than the previous horizontal wrapping layout.
- **Text readability** — all font sizes bumped to 12px minimum. Previously many labels were 6–10px using `--muted` / `--dim` colors making them nearly unreadable on dark backgrounds. Everything now uses brighter text colors.
- **Wider layout** — mobile max-width loosened to 560px, desktop capped at 900px. More breathing room throughout.
- **Color brightness** — all accent colors (gold, purple, hit, crit, heavy, CC, green, red) brightened across the board. Better contrast on dark backgrounds.

### Branding
- App now branded with character name (OhStoopKid), guild (KWTD), and server (Ascension · Americas)
- Browser tab title updated to `OhStoopKid · TnL PvP Stat Calculator`

### Analytics
- Added Google Analytics (GA4) tracking
- Custom events: tab views, perspective toggles, preset clicks (with type: t3/zero/cap), mode selection, slider interactions, explanation opens, resource link clicks, feedback button clicks

### Responsive Layout
- Full desktop dashboard layout — two-column on 768px+ screens (presets/explanations left, sliders/results right)
- Formula tab goes 2×2 grid on desktop
- Resources tab goes 2-column grid on desktop
- Collapsible explanations auto-expand on desktop

### New Files
- `CONTRIBUTING.md` — contribution guide for external developers, includes formula sources, stat ranges, code style, and testing checklist
- `README.md` — full documentation with live link, tab breakdown, cap table, real T3 stat ranges, preset guide, and formulas

---

## v1.1 — March 30, 2026

### New Features
- **Attacker / Defender perspective toggle** — global switch that flips all four tabs simultaneously. Defender mode shows your defensive outcome (Dodge %, Crit Blocked %, Heavy Resisted %, CC Resisted %) rather than the attacker's offensive outcome. Gap colours invert so green always means good for you.
- **🔗 Links tab** — resources, feedback, patch note sources, and build guide references all in one place
- **Feedback button** — direct link to GitHub Issues from inside the app
- **Zero Stat presets (pink)** — loads the exact scenarios where the patch actually fires at T3: zero hit, zero endurance, zero CC chance, zero CC resist

### Stat Range Updates
Based on real T3 unbuffed gear screenshots:
- Hit updated to ~4,800+ (was 2,200–4,000 estimate)
- Evasion updated to ~5,100 (confirmed)
- Magic Heavy Atk updated to ~2,450 / Melee Heavy ~1,500 (was ~2,000 estimate)
- Heavy Eva updated to ~200–300 typical (was ~1,200 estimate) — dedicated counter build ~2,449
- Crit updated to ~3,000 base (was ~3,300 estimate)
- CC Resist updated to ~3,400 — edges CC Chance (~3,100) at base gear
- All slider maximums raised to 7,000 to accommodate buffed in-combat values

### Preset Overhaul
Three tiers per tab:
- 🟢 **Green** — real T3 meta matchups from actual gear screenshots
- 🩷 **Pink** — zero-stat scenarios showing maximum patch impact
- 🔴 **Red** — exact cap threshold values where the patch starts firing

### Content Updates
- **Crit tab explanation** — added guaranteed crit dagger mechanic note and Lightning Infusion burst window (+600 crit at <50% HP)
- **Heavy tab explanation** — updated to reflect real Heavy Eva numbers (~200–300 typical)
- **CC tab explanation** — updated to reflect CC Resist edging CC Chance at T3 base gear
- **Patch tab** — replaced Steelheart-specific section with ranked "Where the Patch Actually Fires" card. Added T4 prep community confirmation.

### Bug Fixes
- Fixed "Battlefield" → "Battlegrounds" throughout
- Fixed Hit/Eva, Crit/End, Heavy, CC defender perspective math
- Fixed Links tab not rendering (nested inside patch section)
- Fixed feedback button not visible

---

## v1.0 — March 30, 2026

### Initial Release
- Hit / Evasion, Crit / Endurance, Heavy Attack, CC Chance calculators
- Pre vs Post patch comparison table on every tab
- Per-mode result grid (Pre / Open World / Battlegrounds / Arena)
- T3 meta presets and cap threshold presets
- Dynamic analysis box
- Collapsible explanations per stat tab
- Formulas tab and Patch tab
