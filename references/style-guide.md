# Pixel Terminal UI Style Guide

## One-Line Style

Dark macOS-native pixel terminal UI: a compact black control surface for developer workflows, blending notch-like pill morphology, terminal typography, semantic agent status colors, subtle grain/dither texture, and restrained glass depth.

## Visual DNA

- **Native control surface**: the UI should feel mounted to the OS: menu bar, notch, top overlay, command palette, dock-like status, or compact dashboard.
- **Pixel terminal layer**: use pixel display fonts, monospaced labels, ASCII animation, code diffs, terminal rows, crisp icons, and low-resolution texture.
- **Black object first**: the core surface is an object: pure black or ink black, with soft shadow, faint stroke, and limited translucency.
- **State over decoration**: color appears because something is happening, not because the page needs flair.
- **Compact density**: prioritize glanceable rows, status chips, keyboard hints, and clear actions.

## Palette

Use a neutral black base with semantic accents.

```css
:root {
  --pt-bg: #111111;
  --pt-bg-deep: #050505;
  --pt-surface: #151518;
  --pt-ink: #000000;
  --pt-panel: rgba(24, 24, 27, 0.88);
  --pt-glass: rgba(255, 255, 255, 0.06);
  --pt-border: rgba(255, 255, 255, 0.10);
  --pt-border-strong: rgba(255, 255, 255, 0.18);
  --pt-text: #e5e5e5;
  --pt-text-soft: rgba(255, 255, 255, 0.72);
  --pt-text-dim: rgba(255, 255, 255, 0.42);
  --pt-orange: #d97757;
  --pt-green: #22c55e;
  --pt-green-bright: #4ade80;
  --pt-blue: #3b82f6;
  --pt-blue-bright: #60a5fa;
  --pt-alert: #f97316;
  --pt-cyan: #06b6d4;
  --pt-purple: #a855f7;
  --pt-red: #f87171;
}
```

## Typography

- Display/headline: `Departure Mono`, `Geist Pixel Square`, `Press Start 2P`, or a similar pixel/mono display face.
- Code/status: `JetBrains Mono`, `SF Mono`, `ui-monospace`.
- Body/UI: `-apple-system`, `BlinkMacSystemFont`, `SF Pro Text`, `Segoe UI`, `system-ui`.
- Do not use negative letter spacing. Pixel headings can use slight positive tracking.
- Keep hero-scale type only for hero sections. Use small tight labels inside panels.

## Layout Rules

- Use a top-centered pill/notch for primary live status when the product allows it.
- If expanded, the panel should feel like the pill grew downward, not like an unrelated card appeared.
- Rows should be dense but calm: 8-12px vertical padding, 6-10px gaps, subtle dividers.
- Buttons are compact, icon-capable, and action-specific. Use keyboard hints for developer flows.
- Avoid nested cards. Use black surfaces, rows, strips, and segmented controls.

## Motion

- Use motion for state changes:
  - running: animated bars or low-amplitude waveform.
  - waiting: breathing/pulsing dot or two pause bars.
  - text cycling: ASCII scramble using `01+-*:.`.
  - expanded panel: springy height/width morph from the pill.
- Provide reduced-motion fallbacks.

## Texture

Use subtle, almost background-level texture:

- grain/noise opacity: 0.08-0.16.
- god-ray/dither opacity: 0.10-0.25.
- ASCII scatter behind hero/status only, never over readable content.

## Avoid

- Bright cyberpunk neon everywhere.
- Generic SaaS bento cards as the primary structure.
- Decorative gradient blobs/orbs.
- Marketing-heavy hero pages when a working tool should be shown.
- Random purple-blue gradients dominating the screen.
- Copying Apple/Vibe Island assets directly.
