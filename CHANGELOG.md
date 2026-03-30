# Changelog

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
- **Crit tab explanation** — added guaranteed crit dagger mechanic note (coded as ~infinite crit stat, BG cap catches it at 75%) and Lightning Infusion burst window (+600 crit at <50% HP)
- **Heavy tab explanation** — updated to reflect real Heavy Eva numbers (~200–300 typical). Heavy attack is near-uncontested at T3 — either ~70% proc vs typical opponents or completely shut down by a dedicated ~2,449 counter build. No middle ground.
- **CC tab explanation** — updated to reflect CC Resist edging CC Chance at T3 base gear. Both sides have buff sources pushing hundreds higher — timing your CC is the real skill expression.
- **Patch tab** — Steelheart-specific section replaced with ranked "Where the Patch Actually Fires" card using real numbers and impact ratings. Added T4 prep community confirmation.

### Bug Fixes
- Fixed "Battlefield" → "Battlegrounds" throughout the entire app
- Fixed Hit/Eva defender perspective — was passing evasion as the hit arg to the formula
- Fixed Crit/Endurance defender perspective — was passing endurance as the crit arg
- Fixed Heavy Atk/Eva defender perspective — same issue as Crit
- Fixed CC defender perspective — was showing attacker land rate instead of defender resist rate; also removed incorrect arg swap that caused CC% to increase when resist increased in defender mode
- Fixed Links tab not rendering — sec-resources was nested inside sec-patch due to missing closing div
- Fixed feedback button not visible — same nesting issue

---

## v1.0 — March 30, 2026

### Initial Release
- Hit / Evasion calculator with threshold mechanic
- Crit / Endurance calculator with glancing hit formula
- Heavy Attack / Heavy Evasion calculator
- CC Chance / CC Resist calculator with unique base % formula
- Pre vs Post patch comparison table on every tab
- Per-mode result grid (Pre / Open World / Battlegrounds / Arena)
- T3 meta presets and cap threshold presets
- Dynamic analysis box
- Collapsible explanations per stat tab
- Formulas tab with full math and worked examples
- Patch tab with cap values table and impact ranking
