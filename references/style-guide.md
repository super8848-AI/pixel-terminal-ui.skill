# Pixel Terminal UI Style Guide

## One-Line Style

Dark macOS-native pixel terminal UI: a compact black control surface for developer workflows, blending notch-like pill morphology, pixel/terminal typography, semantic agent status colors, sparse binary scatter, grain, god-ray/dither texture, and restrained glass depth.

## Visual DNA

- **Native control surface**: the UI should feel mounted to the OS: menu bar, notch, top overlay, command palette, dock-like status, or compact dashboard.
- **Pixel terminal layer**: use pixel display fonts, monospaced labels, ASCII/binary animation, code diffs, terminal rows, crisp icons, and low-resolution texture.
- **Black object first**: the core surface is an object: pure black or ink black, with soft shadow, faint stroke, and limited translucency.
- **State over decoration**: color appears because something is happening, not because the page needs flair.
- **Compact density**: prioritize glanceable rows, status chips, keyboard hints, and clear actions.
- **Website-scale atmosphere**: behind the main UI, use sparse `0 1 + - * : .` scatter, a top-centered pale god-ray, and tiny grain. Keep it quiet enough that screenshots still read as black.

## Palette

Use a neutral black base with semantic accents.

```css
:root {
  --pt-bg: #111111;
  --pt-bg-deep: #050505;
  --pt-bg-soft: #1a1a1a;
  --pt-surface: #151518;
  --pt-ink: #000000;
  --pt-terminal: #1e1e1e;
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
  --pt-yellow: #f59e0b;
  --pt-red: #f87171;
  --pt-diff-red-bg: rgba(153, 27, 27, 0.50);
  --pt-diff-green-bg: rgba(22, 101, 52, 0.50);
}
```

## Semantic Color Mapping

Use the same restraint as the reference site: one accent per state or tool identity.

- Base text: `#e5e5e5`; muted text: white at 42-72% opacity.
- Product/action orange: `#d97757`.
- Done/approved/Codex green: `#22c55e` or bright `#4ade80`.
- Running/jump/Gemini blue: `#3b82f6` or bright `#60a5fa`.
- Permission/attention orange: `#f97316`.
- Question/interactive scatter cyan: `#06b6d4`.
- Exploration/Cursor purple: `#a855f7`.
- OpenCode/alternate warm yellow: `#f59e0b`.
- Errors or deleted diff: soft red text with dark red backing, not full neon red blocks.

## Typography

- Latin display/headline: `Geist Pixel Square`, `Departure Mono`, `Press Start 2P`, or a similar pixel/mono display face.
- Chinese display/headline: `Zpix`, `Fusion Pixel 12px Monospaced SC`, `Fusion Pixel`, `Ark Pixel 12px zh_cn`, `Noto Sans Mono CJK SC`, then `PingFang SC` fallback. For Chinese headings, prefer true bitmap/pixel CJK fonts over smooth system sans. A known working web source for Zpix is `https://cdn.jsdelivr.net/gh/SolidZORO/zpix-pixel-font@master/website/zpix.woff2`.
- Code/status: `JetBrains Mono`, `SF Mono`, `ui-monospace`.
- Body/UI: `-apple-system`, `BlinkMacSystemFont`, `SF Pro Text`, `Segoe UI`, `PingFang SC`, `Noto Sans CJK SC`, `system-ui`.
- Do not use negative letter spacing. Pixel headings can use slight positive tracking.
- Keep hero-scale type only for hero sections. Use small tight labels inside panels.
- For Chinese pixel fonts, keep line-height at `1.45-1.7`; use them for headings, short labels, chips, and hero words. Do not use pixel Chinese fonts for paragraph body copy; use system Chinese fonts for readability.
- Avoid glow or blur shadows on Chinese pixel headlines. If the glyphs look fuzzy, remove `text-shadow`, avoid CSS transforms on the text itself, and prefer integer-ish font sizes with `-webkit-font-smoothing: none`.

## Layout Rules

- Use a top-centered pill/notch for primary live status when the product allows it.
- If expanded, the panel should feel like the pill grew downward, not like an unrelated card appeared.
- Use notch dimensions close to real utility surfaces: compact around `240px x 36px`; expanded panels can grow to `420-520px` wide with `14px` bottom radius.
- Rows should be dense but calm: 8-12px vertical padding, 6-10px gaps, subtle dividers.
- Buttons are compact, icon-capable, and action-specific. Use keyboard hints for developer flows.
- Avoid nested cards. Use black surfaces, rows, strips, and segmented controls.
- For website sections, let the primary screenshot/mockup fade out with a vertical mask rather than ending in a hard rectangular block.

## Motion

- Use motion for state changes:
  - running: animated bars or low-amplitude waveform.
  - waiting: breathing/pulsing dot or two pause bars.
  - text cycling: ASCII scramble using `01+-*:.`.
  - expanded panel: springy height/width morph from the pill.
- Use the reference spring feel: `cubic-bezier(.175, .885, .32, 1.1)` for pill growth and hover lifts.
- Provide reduced-motion fallbacks.

## Texture

Use subtle, almost background-level texture:

- grain/noise opacity: 0.08-0.16; generate a small `128px` tile or use CSS noise.
- god-ray opacity: 0.10-0.25, top-center origin, white or slightly warm.
- optional ordered dither: 4x4 Bayer pattern or CSS grid dots, used only on god-rays or image masks.
- binary/ASCII scatter: characters `0 1 + - * : .`, around `10px` desktop cells and `14px` mobile cells. Fade from a corner or behind the hero/status only, never over readable content.
- MacBook/product screenshots: use mask fade `linear-gradient(to bottom, black 70%, transparent 95%)` when the bottom edge would feel too hard.

## Avoid

- Bright cyberpunk neon everywhere.
- Generic SaaS bento cards as the primary structure.
- Decorative gradient blobs/orbs.
- Marketing-heavy hero pages when a working tool should be shown.
- Random purple-blue gradients dominating the screen.
- Copying Apple/Vibe Island assets directly.
