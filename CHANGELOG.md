# Changelog

## v1.2 — April 1, 2026

### UI Overhaul (credit: Frank / Frankie-hz — Issues #1, PR #2)
- **3-column preset grid** — all four stat tabs now have labeled preset columns: 🟢 T3 Meta / 🩷 Zero Stat / 🔴 Cap Thresholds. Much easier to scan than the previous horizontal wrapping layout. Frank identified the pattern and submitted a PR for the Crit/End tab which was the last remaining tab to get the update.
- **Text readability** — all font sizes bumped to 12px minimum throughout. Previously many labels were 6–10px using `--muted` / `--dim` colors, nearly unreadable on dark backgrounds. Everything now uses `--text` (bright) or higher-contrast colors.
- **Wider layout** — mobile max-width loosened to 560px, desktop capped at 900px. More breathing room throughout.
- **Color brightness** — all accent and text colors brightened across the board. Better contrast on the dark background.

### Branding
- Header now shows: `THRONE & LIBERTY · ASCENSION · AMERICAS`
- Subtitle: `by OhStoopKid · KWTD · March 31, 2026 Patch`
- Footer: `v1.2 · OhStoopKid · KWTD · Ascension · Americas`
- Browser tab title: `OhStoopKid · TnL PvP Stat Calculator`

### Analytics
- Added Google Analytics (GA4) with measurement ID `G-D8GEVYZQS0`
- Custom events tracking:
  - `tab_view` — which tab was opened
  - `perspective_toggle` — attacker/defender switch
  - `preset_click` — which preset, which type (t3/zero/cap), which tab
  - `mode_select` — Pre/Open World/Battlegrounds/Arena per tab
  - `slider_used` — first slider interaction per tab per session
  - `explanation_open` — which collapsible explanations get read
  - `resource_click` — which external links get clicked
  - `feedback_click` — feedback button taps

### Responsive Desktop Layout
- Two-column dashboard on 768px+ — presets/explanations left, sliders/results right
- Sliders stay above results on the right column
- Formula tab goes 2×2 grid on desktop
- Resources tab goes 2-column grid on desktop
- Collapsible explanations auto-expand on desktop (no tap required)
- Large desktop (1100px+) widens left column to 420px

### Bug Fixes
- Fixed Crit/End defender perspective — big number now shows Crit Blocked % (100 − crit%) in defender mode, consistent with Hit/Eva showing Dodge %, Heavy showing Heavy Resisted %, CC showing CC Resisted %
- Fixed Heavy defender perspective — same display inversion
- Fixed CC defender perspective — increasing CC Resist now correctly decreases CC received chance
- Fixed all four stat tabs reading raw slider values directly in defender mode, bypassing the `ga()`/`gd()` swap that was causing incorrect formula inputs

### New Files
- `CONTRIBUTING.md` — contributor guide with formula sources, stat ranges, code style, testing checklist
- `CHANGELOG.md` — this file

---

## v1.1 — March 30, 2026

### New Features
- **Attacker / Defender perspective toggle** — global switch flipping all four tabs simultaneously. Defender mode shows Dodge %, Crit Blocked %, Heavy Resisted %, CC Resisted %. Gap colors invert so green always means good for you.
- **Links tab** — resources, feedback, patch note sources, build guide references
- **Feedback button** — direct link to GitHub Issues from inside the app
- **Zero Stat presets** — loads exact scenarios where the patch fires at T3

### Stat Range Updates
Based on real T3 unbuffed gear screenshots:
- Hit ~4,800+ / Evasion ~5,100
- Magic Heavy ~2,450 / Melee Heavy ~1,500
- Heavy Eva ~200–300 typical / ~2,449 dedicated counter
- Crit ~3,000 base / Endurance ~3,500
- CC Chance ~3,100 / CC Resist ~3,400

### Bug Fixes
- Fixed "Battlefield" → "Battlegrounds" throughout
- Fixed Hit/Eva, Crit/End, Heavy, CC defender perspective math
- Fixed Links tab not rendering (nested inside Patch section)
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
- Formulas tab with full math and worked examples
- Patch tab with cap values table and impact ranking
