# Pixel Terminal UI Skill

A Codex skill for creating dark macOS-native pixel terminal interfaces: compact black control surfaces, notch/top-bar pill morphology, terminal typography, semantic live states, subtle grain/dither texture, and developer-tool density.

This style was distilled from the Vibe Island / Open Island design language, then generalized so it can be reused in coding products, dashboards, agent monitors, command centers, approval panels, and product intro pages.

## Install

```bash
npx skills add super8848-AI/pixel-terminal-ui.skill
```

## When To Use

Use this skill when you want a product interface that feels like:

- 像素终端风 UI
- Vibe Island / Open Island inspired UI
- macOS notch or Dynamic Island style control surface
- dark terminal dashboard
- AI coding agent monitor
- developer command center
- compact permission / approval panel
- game, tool, or product intro page with terminal HUD styling

Example request:

```text
调用 pixel-terminal-ui skill，帮我生成一个产品介绍 HTML，内容关于热门游戏介绍。
```

## Design DNA

The core direction is:

> A dark macOS-native pixel terminal UI: a compact black control surface for developer workflows, blending notch-like pill morphology, terminal typography, semantic agent status colors, subtle grain/dither texture, and restrained glass depth.

Key traits:

- Black or near-black surfaces first, decoration second.
- Pixel/mono display typography for headings and status labels.
- Dense terminal rows, command output, code/diff panels, and keyboard hints.
- Color is semantic: green done, blue running, orange attention, cyan question, red error.
- Texture is subtle: grain, dither, ASCII scatter, scanline hints.
- UI should feel useful before it feels stylish.

## Repository Structure

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── style-guide.md
│   ├── component-patterns.md
│   └── core-prompt.md
└── examples/
    ├── README.md
    └── hot-games-product-intro.prompt.md
```

## Files

- `SKILL.md` defines the skill trigger, workflow, and implementation bias.
- `agents/openai.yaml` provides display metadata for agent UIs.
- `references/style-guide.md` captures the visual grammar, palette, typography, layout, motion, and avoid rules.
- `references/component-patterns.md` includes reusable CSS, React component patterns, and ASCII text animation snippets.
- `references/core-prompt.md` contains an English prompt and a Chinese short prompt for applying the style.
- `examples/` contains reusable example prompts and implementation directions.

## Quick Prompt

```text
Design a dark macOS-native pixel terminal interface for a developer workflow product. The UI should feel like a compact control surface mounted to the operating system: a black notch/top-bar pill that can expand into a notification or session panel, with dense terminal-inspired rows, code/diff context, keyboard hints, and semantic live states. Blend native macOS restraint with retro terminal texture: pixel/monospace display typography, subtle ASCII scatter, faint grain/noise, ordered dither or soft god-ray texture, pure black surfaces, soft shadows, thin translucent borders, and very limited glass blur. Use color only as state language: green for ready/done, blue for running, orange for permission/attention, cyan for questions, purple only for exploration/tool identity, red for errors. The product should look functional first, not like a generic SaaS landing page. Avoid decorative gradient blobs, heavy neon cyberpunk, beige palettes, oversized cards, and copied Apple/Vibe Island assets. Prioritize a real usable dashboard/control panel over marketing composition.
```

## Implementation Checklist

Before shipping a page or component in this style, check:

- The first screen shows a real usable interface, not only marketing copy.
- Text does not overflow on mobile or desktop.
- Cards are not nested inside cards.
- Black surfaces carry the structure; accents only express state.
- Pixel/terminal effects do not reduce readability.
- Motion has a reduced-motion fallback.
- The UI remains understandable without grain, ASCII, or animation.
