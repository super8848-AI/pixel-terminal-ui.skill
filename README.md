# Pixel Terminal UI Skill

A Codex skill for creating Vibe Island-inspired dark pixel terminal interfaces: compact black notch controls, pixel/mono typography, semantic live states, binary `01` scatter, god-ray/dither texture, and developer-tool density.

The style is distilled from the public Vibe Island website and generalized for coding products, dashboards, agent monitors, command centers, approval panels, game pages, and product intro pages. Do not copy Vibe Island assets; reuse the design principles.

## Install

```bash
npx skills add super8848-AI/pixel-terminal-ui.skill
```

## When To Use

Use this skill when you want:

- 像素终端风 UI
- Vibe Island / Open Island inspired UI
- macOS notch or Dynamic Island style control surface
- dark terminal dashboard
- AI coding agent monitor
- developer command center
- compact permission / approval panel
- game, tool, or product intro page with terminal HUD styling

## Design DNA

The core direction is:

> A dark macOS-native pixel terminal UI: a compact black control surface for developer workflows, blending notch-like pill morphology, pixel/terminal typography, semantic agent status colors, sparse binary scatter, grain, god-ray/dither texture, and restrained glass depth.

Key traits:

- Black or near-black surfaces first, decoration second.
- Pixel/mono display typography for headings and status labels.
- Chinese headings should use pixel-capable CJK fonts such as `Zpix`, `Fusion Pixel`, `Ark Pixel`, or `Noto Sans Mono CJK SC`.
- Sparse binary/ASCII background uses `0 1 + - * : .`, usually faded from a corner.
- God-ray light, 128px grain, 4x4 ordered dither, and MacBook/screen fade masks are used subtly.
- Color is semantic: orange attention/product, green done, blue running, cyan question, purple exploration, red error.
- UI should feel useful before it feels stylish.

## Repository Structure

```text
.
├── SKILL.md
├── README.md
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

## Quick Prompt

```text
做一个参考 Vibe Island 官网气质但不复制素材的暗黑像素终端风 macOS 原生控制界面：纯黑 notch 状态 pill、像素/等宽字体、中文像素字体、二进制 01 背景、轻微颗粒、顶部 god-ray、可选有序抖动、黑色实体面板、细边框和柔和阴影。颜色只表达状态：橙=产品/注意，绿=完成，蓝=运行，青=提问，紫=探索，红=错误。避免通用 SaaS 卡片、霓虹赛博、渐变光球和营销页感，优先做可用的控制台/仪表盘。
```

## Implementation Checklist

- First screen shows a real usable interface, not only marketing copy.
- Chinese headings use pixel-capable CJK fonts where possible.
- Binary/ASCII texture does not cover readable content.
- Text does not overflow on mobile or desktop.
- Cards are not nested inside cards.
- Black surfaces carry the structure; accents only express state.
- Motion has a reduced-motion fallback.
- UI remains understandable without grain, god-rays, ASCII, or animation.
