# Contributing to TnL PvP Stat Calculator

Thanks for wanting to help — contributions are welcome. Here's everything you need to know before submitting.

---

## How to Contribute

1. **Fork** the repo
2. **Make your changes** in your fork
3. **Test on both mobile and desktop** before submitting
4. **Open a Pull Request** back to `main` with a clear description of what you changed and why

For anything beyond a small bug fix, **open an Issue first** so we can discuss before you spend time building it.

---

## Project Structure

This is an intentionally simple single-file app — no build tools, no frameworks, no dependencies beyond two Google Fonts.

```
index.html          ← the entire app lives here
README.md
CHANGELOG.md
CONTRIBUTING.md
```

Everything is in `index.html`:
- **CSS** — in the `<style>` block, mobile-first with `@media` breakpoints for desktop
- **HTML** — six tab sections (`sec-hit`, `sec-crit`, `sec-heavy`, `sec-cc`, `sec-formula`, `sec-patch`, `sec-resources`)
- **JS** — in the `<script>` block at the bottom

Please keep it as a single file. No build steps, no npm, no bundlers.

---

## Formula Sources

The stat formulas are confirmed from Maxroll's in-depth stats guide and community testing. If you're changing any formula logic, link your source in the PR description. Don't change formulas based on tooltips alone — in-game tooltips in TnL are often misleading.

**Current confirmed formulas:**

| Stat Pair | Formula |
|-----------|---------|
| Hit / Evasion | `Miss% = (Eva−Hit) / (Eva−Hit + 1000) × 100%` |
| Crit / Endurance | `Crit% = (Crit−End) / (Crit−End + 1000) × 100%` |
| Heavy Atk / Heavy Eva | Same formula as Crit/End |
| CC Chance / Resist | `CC% = Z + W × [gap/(250+gap)]` (see CC tab for full formula) |
| Skill Damage Boost | `Damage × (1 + SDB/(1000+SDB))` |
| Defense | `Damage × (1 / (1 + Defense/2750))` — level 55 |

Patch caps (March 31, 2026) apply to the effective gap fed into each formula, not the raw stat values.

---

## Stat Ranges

T3 numbers used in presets are based on real unbuffed gear screenshots, not estimates. If you're updating presets, please have a source — questlog.gg build screenshots, Maxroll build guides, or your own character sheet.

Current confirmed T3 unbuffed ranges:
- Hit: ~4,800+ / Evasion: ~5,100
- Crit: ~3,000 base / Endurance: ~3,500
- Magic Heavy Atk: ~2,450 / Melee Heavy Atk: ~1,500
- Heavy Eva: ~200–300 typical / ~2,449 dedicated counter build
- CC Chance: ~3,100 / CC Resist: ~3,400

Both sides can push higher with in-combat buffs.

---

## What's In Scope

Good PRs:
- Bug fixes with a clear explanation of what was wrong
- New presets backed by real T3 data
- Formula corrections with a source
- UI improvements that work on mobile and desktop
- New stat mechanics that have confirmed formulas (link source)
- Responsive layout improvements

Please open an Issue first for:
- New tabs or major new sections
- Changes to the formula logic
- Anything that affects how the perspective toggle works

Out of scope:
- Adding external dependencies or build tools
- Splitting into multiple files
- PvE damage calculations (different tool, different scope)

---

## Code Style

- Keep it readable — this file gets edited by people who aren't full-time devs
- Don't minify anything manually — the file is already compact enough
- Mobile-first CSS — test at 375px width before desktop
- Perspective toggle logic: attacker/defender swap is handled by reading raw slider values directly, never through `ga()`/`gd()` for the Hit tab — see comments in the JS if you're touching that section
- All four stat tabs follow the same pattern: `dash-left` (presets/explanations) and `dash-right` (sliders/results) for desktop layout

---

## Testing Checklist

Before opening a PR:

- [ ] Works on mobile (375px width) — no horizontal scroll, no clipped content
- [ ] Works on desktop (1200px+) — two-column layout intact
- [ ] Attacker and Defender perspective both show correct results
- [ ] All four mode buttons (Pre / Open World / Battlegrounds / Arena) produce correct output
- [ ] Pre vs Post compare table shows correct delta
- [ ] No broken references or JS errors in browser console

---

## Questions

Open an Issue or DM on Discord. The GitHub Issues page is the preferred place for bug reports and feature discussions so the whole community can see them.
