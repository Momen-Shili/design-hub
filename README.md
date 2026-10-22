# design-hub

One entry point for all your design skills. `design-hub` is a small router skill for Claude: you type a short shortcut like `be` or `security-product`, and it loads the matching design skill(s) and applies them with consistent rules.

```
/design-hub en scan results dashboard
/design-hub be pricing section
/design-hub security-product full frontend
/design-hub pick landing page for a security startup
/design-hub list
```

It does **not** contain the design styles themselves. It maps a shortcut to a style skill you already have installed, so the real style rules are always loaded from the source skill and never paraphrased from memory.

## Why

With 60+ design style skills installed, nobody remembers their exact names. design-hub gives every style a 2-letter code, groups them by category, adds ready-made combinations (recipes), and enforces a few pairing rules so products don't end up with five clashing looks.

## Requirements

- [Claude Code](https://claude.com/claude-code) or any Claude client that supports skills and slash commands.
- The design style skills you want to call. This repo only references them by name. The 67-style set it was built around comes from the [awesome-design-skills](https://github.com/bergside/awesome-design-skills) collection by bergside. Check that repository for its license and install the styles you want.
- Optional helper skills used by the helper shortcuts: design system, brand, banner design, slides, UI styling, frontend design, 3D web experience, glassmorphism, image-to-code, dataviz and scroll-world.

A shortcut whose target skill is not installed simply can't load. design-hub should tell you which skill is missing.

## Install

Clone straight into your skills folder:

```bash
git clone https://github.com/Momen-Shili/design-hub ~/.claude/skills/design-hub
```

Or copy the folder manually so you end up with `~/.claude/skills/design-hub/SKILL.md`.

## Usage

`/design-hub <shortcut> <what to build>`

- A shortcut is a 2-letter code (`be`), the style name (`bento`) or a recipe name (`saas-app`).
- Give two shortcuts to combine them: the first is the primary style for the whole product, the second is an accent for specific sections.
- `list` prints every shortcut. `pick <description>` asks at most one question, then recommends one primary style and one accent with the exact call to run.

### What it does on every call

1. Resolves the shortcut (or shows the closest three if unknown).
2. Loads the mapped skill(s) before writing any UI.
3. Applies the style's tokens, typography, spacing and components.
4. Applies the pairing rules below.
5. Always defines design tokens first, keeps the layout responsive, supports dark mode when the style allows it, meets WCAG 2.2 AA contrast and respects reduced motion.
6. Ends by stating which shortcut(s) were used.

## Shortcuts

### Clean and minimal
`cn` clean · `mi` minimal · `sl` sleek · `sp` spacious · `fl` flat · `ge` geometric · `cx` codex · `sq` square · `rf` refined · `mo` modern · `ct` contemporary · `ba` basic

### Product, SaaS and enterprise
`en` enterprise · `an` ant · `sh` shadcn · `cp` corporate · `pf` professional · `rk` roku · `ma` material · `ag` agentic · `lv` levels · `be` bento

### Bold and expressive
`bo` bold · `po` power · `pr` premium · `dr` dramatic · `ar` artistic · `ex` expressive · `cr` creative · `pu` pulse · `co` colorful · `vb` vibrant · `gr` gradient · `ip` impeccable

### Dark, tech and futuristic
`fu` futuristic · `cs` cosmic · `ne` neon · `mx` matrix · `mn` mono

### Depth and materials
`gl` glassmorphism · `nu` neumorphism · `cl` claymorphism · `sm` skeumorphism · `pe` perspective

### Raw and brutalist
`br` brutalism · `nb` neobrutalism

### Playful, hand-made and retro
`do` doodle · `sk` sketch · `fi` fiction · `li` lingo · `fr` friendly · `cf` cafe · `fa` fantasy · `im` immersive · `pc` pacman · `sg` sega · `tt` tetris · `di` dithered · `re` retro · `vi` vintage · `ri` riso

### Editorial and print
`ed` editorial · `pa` paper · `iv` ivory-journal · `sy` storytelling · `tc` terracotta · `st` stitch · `ux` ui-ux-pro-max

### Helper shortcuts (tools, not styles)

| Code | Use it for |
|---|---|
| `tok` | Design tokens and component specs |
| `brand` | Voice, identity, brand consistency |
| `logo` | Logos, icons, corporate identity |
| `ban` | Banners for social, ads, web, print |
| `sld` | Strategic HTML presentations |
| `ui` | shadcn/ui, Tailwind, accessible components |
| `fe` | Distinctive, non-templated UI direction |
| `3d` | Three.js and React Three Fiber scenes |
| `gx` | Advanced frosted-glass effects |
| `i2c` | Build a site from generated design images |
| `dv` | Charts, dashboards, stat tiles |
| `sw` | Scroll-scrubbed fly-through landing pages |

## Recipes

| Recipe | Loads | Notes |
|---|---|---|
| `saas-app` | en + sh + tok | Product UI with shared tokens |
| `security-product` | en (app) + po (landing) + tok | Trust-first and dark; add `3d` for the hero only |
| `b2b-landing` | po + lv | Premium look with a conversion focus |
| `dashboard-data` | en + dv | Data-dense dashboards and reports |
| `docs-site` | ed + pa | Readable long-form content |
| `portfolio-retro` | sg or pc + di | Retro-OS or game-style personal site |
| `portfolio-clean` | cn + be | Simple, scannable portfolio |
| `consumer-app` | fr + li | Friendly, rounded, mobile-first UI |
| `agency-site` | ar + dr | Creative studio with strong visuals |
| `brand-kit` | brand + tok + logo | Identity, tokens and assets together |
| `pitch-deck` | sld + tok | Investor or client presentation |

## Pairing rules

- At most **two visual styles per product**: one for the app UI, one for public or marketing pages.
- For B2B, security, finance and health products, avoid playful styles (`pc`, `sg`, `tt`, `ri`, `sk`, `do`, `cl`, `nb`, `fi`, `li`) in the product UI. They are fine for portfolios, games and consumer apps.
- 3D belongs only in a landing hero: lazy-load it, keep the model under about 3 MB, provide a mobile fallback and honour reduced motion.
- Any chart or dashboard also loads `dv`.
- Shared tokens come from `tok` so both styles stay consistent.

## Customising

- **Change a code:** edit the tables in `SKILL.md`. Keep codes unique.
- **Add a style:** install its skill, then add one row with a free 2-letter code.
- **Add a recipe:** add a row to the recipes table with the codes it loads.
- Seven styles (`vb`, `tt`, `vi`, `sy`, `tc`, `st`, `ux`) ship without a one-line description; their details load when invoked.

## Repository layout

```
design-hub/
├── SKILL.md     # the router skill (add it here)
├── README.md
└── LICENSE
```

## Contributing

Issues and pull requests are welcome, especially new recipes and pairing rules.

## License

MIT © Momen Shili. The design styles referenced here belong to their own authors and licenses.
