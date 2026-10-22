---
name: "design-hub"
description: "Shortcut router for all installed design skills. Call /design-hub with a code, style or recipe plus what to build to apply a visual style (bento, glass, enterprise, retro) or a ready combo."
---

# Design Hub: one entry point for every installed design skill

This skill does not hold design rules itself. It maps a short shortcut to the right installed design skill(s), loads them, and applies them with consistent pairing rules.

## How to call it

`/design-hub <shortcut> <what to build>`

Examples:
- `/design-hub en scan results dashboard`
- `/design-hub be pricing section`
- `/design-hub security-product full frontend`
- `/design-hub list` shows every shortcut
- `/design-hub pick <description>` recommends one or two styles and explains why

A shortcut can be a 2-letter code, the full style name, or a recipe name. Two shortcuts can be given: the first is the primary style for the whole product, the second is an accent for specific sections.

## Procedure

1. Resolve the shortcut with the tables below. If it is unknown, show the three closest matches and ask which one.
2. Load the mapped skill(s) with the Skill tool BEFORE writing any UI. Use the skill name as it is listed in the session; it may carry an `anthropic-skills:` prefix. Never reproduce a style from memory.
3. Follow the loaded skill's tokens, typography, spacing and component rules.
4. Apply the pairing rules below.
5. Always: define design tokens first (CSS variables), make the layout responsive, support dark mode when the style allows it, meet WCAG 2.2 AA contrast, and respect reduced-motion.
6. End by stating which shortcut and skill(s) were applied.

## Pairing rules

- Use at most two visual styles per product: one for the app UI, one for the public/marketing pages.
- For B2B, security, finance and health products, avoid playful styles (pc, sg, tt, ri, sk, do, cl, nb, fi, li) in the product UI. Playful styles are fine for portfolios, games and consumer toys.
- 3D (`3d`) belongs only in a landing hero: lazy-load it, keep the model under about 3 MB, give a mobile fallback, and honour reduced-motion.
- Any chart or dashboard visual also loads `dv` (dataviz).
- Shared tokens come from `tok` so both styles stay consistent.

## Style shortcuts (design patterns)

### Clean and minimal
| Code | Style | Use it for |
|---|---|---|
| cn | clean | Whitespace, legible type, limited palette |
| mi | minimal | Stripped-back, restrained colour, maximum focus |
| sl | sleek | Minimalist lines, subtle interactions |
| sp | spacious | Generous whitespace, grid-based layouts |
| fl | flat | 2D, vibrant colours, no 3D effects |
| ge | geometric | Structured shapes, neutral colours |
| cx | codex | Radically minimal blank canvas, black fill, pill controls |
| sq | square | Graceful, delicate type, polished layouts |
| rf | refined | Curated minimal with elegant serif type |
| mo | modern | Contemporary editorial, serif, minimal palette |
| ct | contemporary | Current-era minimal, bento, dark-mode ready |
| ba | basic | Print-inspired, editorial grids for reports |

### Product, SaaS and enterprise
| Code | Style | Use it for |
|---|---|---|
| en | enterprise | Dark cloud-platform dashboards, glass panels, data hierarchy |
| an | ant | Structured, data-dense enterprise web apps |
| sh | shadcn | Minimal monochrome components, utility-first |
| cp | corporate | Brand-aligned, structured enterprise grids |
| pf | professional | Polished, trustworthy business look |
| rk | roku | Purple app dashboard, top-bar navigation, cards |
| ma | material | Google Material, layered surfaces, dynamic theming |
| ag | agentic | Conversational AI-first UI, delegated task flows |
| lv | levels | Conversion-focused, low-friction pages |
| be | bento | Modular card grid, scannable layouts |

### Bold and expressive
| Code | Style | Use it for |
|---|---|---|
| bo | bold | Heavyweight type, high contrast |
| po | power | High-end dark, monochrome, premium brands |
| pr | premium | Apple-inspired precision and polish |
| dr | dramatic | Theatrical high-contrast layouts |
| ar | artistic | High-contrast, creative typography |
| ex | expressive | Personality-driven, bold colour |
| cr | creative | Playful character-driven landing pages |
| pu | pulse | Thick borders, geometric shapes, motion feel |
| co | colorful | Vibrant palettes and gradients |
| vb | vibrant | Details load when invoked |
| gr | gradient | Smooth gradient-rich surfaces |
| ip | impeccable | Editorial-poster look, cream and burnt orange |

### Dark, tech and futuristic
| Code | Style | Use it for |
|---|---|---|
| fu | futuristic | Tech typography, sleek innovation look |
| cs | cosmic | Sci-fi dark themes, neon accents |
| ne | neon | Electric glow, high-contrast pairings |
| mx | matrix | Dark terminal green, monospaced, hairline borders |
| mn | mono | Monospace-driven hacker-chic |

### Depth and materials
| Code | Style | Use it for |
|---|---|---|
| gl | glassmorphism | Frosted translucent layers, luminous borders |
| nu | neumorphism | Soft extruded elements on one surface |
| cl | claymorphism | Soft puffy clay-like shapes |
| sm | skeumorphism | Real-world textures and 3D metaphors |
| pe | perspective | Isometric depth, layered elements |

### Raw and brutalist
| Code | Style | Use it for |
|---|---|---|
| br | brutalism | Raw anti-design, functional minimalism |
| nb | neobrutalism | Bold borders, vivid accents, warm surfaces |

### Playful, hand-made and retro
| Code | Style | Use it for |
|---|---|---|
| do | doodle | Hand-drawn, handwritten fonts |
| sk | sketch | Pencil-illustration look on cream paper |
| fi | fiction | Children's-book cartoon, thick outlines |
| li | lingo | Playful rounded shapes, tactile borders |
| fr | friendly | Rounded elements, soft pastels |
| cf | cafe | Cozy warm tones, soft typography |
| fa | fantasy | Game-inspired premium fantasy |
| im | immersive | Exhibit-style deep green canvas, hard offset shadows |
| pc | pacman | Retro arcade, pixel fonts, 8-bit |
| sg | sega | Arcade VT323 pixel type, chunky pressed buttons |
| tt | tetris | Details load when invoked |
| di | dithered | Dot-pattern retro high-contrast visuals |
| re | retro | Vintage typography, nostalgic palettes |
| vi | vintage | Details load when invoked |
| ri | riso | Two-colour risograph print look |

### Editorial and print
| Code | Style | Use it for |
|---|---|---|
| ed | editorial | Magazine layout, refined serif, reading experiences |
| pa | paper | Paper-textured, print-inspired |
| iv | ivory-journal | Research-journal parchment with a single clay accent |
| sy | storytelling | Details load when invoked |
| tc | terracotta | Details load when invoked |
| st | stitch | Details load when invoked |
| ux | ui-ux-pro-max | Details load when invoked |

## Helper shortcuts (tools, not styles)

| Code | Loads | Use it for |
|---|---|---|
| tok | design-system (ckm) | Design tokens, component specs |
| brand | brand (ckm) | Voice, identity, brand consistency |
| logo | design (ckm) | Logos, icons, corporate identity |
| ban | banner-design (ckm) | Banners for social, ads, web, print |
| sld | slides (ckm) | Strategic HTML presentations |
| ui | ui-styling (ckm) | shadcn/ui, Tailwind, accessible components |
| fe | frontend-design | Distinctive, non-templated UI direction |
| 3d | 3d-web-experience | Three.js and React Three Fiber scenes |
| gx | glassmorphism-advanced | Advanced frosted-glass effects |
| i2c | image-to-code | Build a site from generated design images |
| dv | dataviz | Charts, dashboards, stat tiles |
| sw | scroll-world | Scroll-scrubbed fly-through landing pages |

## Recipes (combos)

| Recipe | Loads | Notes |
|---|---|---|
| saas-app | en + sh + tok | Product UI with shared tokens |
| security-product | en (app) + po (landing) + tok | Trust-first, dark, restrained; add 3d for the hero only |
| b2b-landing | po + lv | Premium look with a conversion focus |
| dashboard-data | en + dv | Data-dense dashboards and reports |
| docs-site | ed + pa | Readable long-form content |
| portfolio-retro | sg or pc + di | Retro-OS or game-style personal site |
| portfolio-clean | cn + be | Simple, scannable portfolio |
| consumer-app | fr + li | Friendly, rounded mobile-first UI |
| agency-site | ar + dr | Creative studio, strong visuals |
| brand-kit | brand + tok + logo | Identity, tokens and assets together |
| pitch-deck | sld + tok | Investor or client presentation |

## `list` and `pick`

- `list`: print the tables above grouped by category.
- `pick <description>`: ask at most one clarifying question (audience, trust level, device), then recommend one primary style and at most one accent, with a one-line reason each and the exact call to run.