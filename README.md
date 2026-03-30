# TnL PvP Stat Calculator
**March 31, 2026 Patch — Throne & Liberty**

A mobile-friendly web calculator for understanding PvP stat interactions after the March 31, 2026 KR patch. Built for guild use to quickly model real T3 matchups, burst windows, and zero-stat edge cases.

🔗 **[Open the Calculator](https://stoopkid713.github.io/TnL3.31.patch.pvpcalc)**

---

## What It Does

The patch introduced **stat gap caps** across all four PvP stat pairs — limiting how much the effective gap fed into each formula can be, per content type. This tool lets you:

- Calculate exact hit/dodge, crit, heavy proc, and CC land rates for any stat combination
- Switch between **Attacker and Defender perspective** with a global toggle
- Compare **Pre-patch vs Post-patch** results across all three modes (Open World, Battlegrounds, Arena)
- Load **real T3 meta presets** based on actual unbuffed gear screenshots
- See exactly **where the patch caps fire** using zero-stat and cap threshold presets
- Read plain-language explanations of how each stat pair works at T3

---

## Tabs

| Tab | What It Covers |
|-----|---------------|
| 🎯 Hit/Eva | Hit chance formula, evasion threshold mechanics, real T3 hit ~4,800 vs eva ~5,100 |
| ⚡ Crit/End | Crit formula, glancing hits, Lightning Infusion burst window (+600 crit at <50% HP) |
| 💥 Heavy | Heavy attack proc formula, why magic heavy (~2,450) is near-uncontested at T3 |
| 🔗 CC | Unique CC formula with base % floor, arms race reality (resist edges chance at T3) |
| 📐 Formulas | Full math for all four stat pairs with worked examples |
| ⚡ Patch | Cap values table, ranked impact of the patch, real T3 stat picture |

---

## Patch Cap Values

| Mode | Hit/Eva, Crit/End, Heavy | CC Chance/Resist |
|------|--------------------------|-----------------|
| Open World | +4,500 / −3,000 | +1,800 / −1,200 |
| Battlegrounds | +3,000 / −2,000 | +1,200 / −800 |
| Arena | +2,250 / −1,500 | +900 / −600 |

---

## Real T3 Stat Ranges (Unbuffed)

Based on actual gear screenshots. Both sides can push higher with in-combat buffs.

| Stat | Unbuffed Range |
|------|---------------|
| Hit Chance | ~4,800+ |
| Evasion | ~5,100 |
| Crit | ~3,000 base / ~3,600 buffed (Lightning Infusion) |
| Endurance | ~3,500 |
| Magic Heavy Atk | ~2,450 |
| Melee Heavy Atk | ~1,500 |
| Heavy Eva | ~200–300 typical / ~2,449 dedicated counter build |
| CC Chance | ~3,100 |
| CC Resist | ~3,400 (edges CC Chance at base gear) |

---

## Where the Patch Actually Fires

| Scenario | Impact |
|----------|--------|
| Zero CC Chance vs max Resist (3,400) | 🟢 High — floor triples land rate from ~5.5% to ~19% in BG |
| Guaranteed crit (dagger mechanic) vs any Endurance | 🟢 High — BG cap catches infinite crit at 75% |
| Zero Hit vs max Evasion (5,100) | 🟡 Medium — BG neg cap reduces miss from ~84% to ~67% |
| Zero Endurance vs buffed Crit (3,600) | 🔴 Low — barely changes (78% → 75%) |
| Typical T3 even matchups | ⚫ No impact — caps never fire at current Global T3 gear ranges |

The patch is T4 forward-planning. At current Global T3 natural gear levels, the caps almost never fire in normal matchups.

---

## Preset Color Guide

- 🟢 **Green** — Real T3 meta matchups from actual gear screenshots
- 🔴 **Red** — Exact cap threshold values where the patch starts firing
- 🩷 **Pink** — Zero-stat scenarios showing maximum patch impact

---

## Formulas

**Hit / Evasion**
```
Eva ≤ Hit  →  100% hit (guaranteed)
Eva > Hit  →  Hit% = 100% − [(Eva−Hit) / (Eva−Hit + 1000)] × 100%
```

**Crit / Endurance**
```
Crit ≤ End  →  0% crit (glancing hits)
Crit > End  →  Crit% = (Crit−End) / (Crit−End + 1000) × 100%
```

**Heavy Atk / Heavy Eva** — Same formula as Crit/Endurance

**CC Chance / Resist**
```
Z = Base land%   W = 1 − Z

Gap > 0:  CC% = Z + W × [gap / (250 + gap)] × 100%
Gap < 0:  CC% = Z × [1 − |gap| / (250 + |gap|)] × 100%
```

---

## Feedback

Found a bug or missing scenario? [Submit an issue](https://github.com/stoopkid713/TnL3.31.patch.pvpcalc/issues/new)

---

*Formula sources: Maxroll.gg in-depth stats guide. Stat ranges from real T3 gear screenshots. Patch notes translated from KR server March 31, 2026 update.*
