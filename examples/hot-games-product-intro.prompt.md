# Hot Games Product Intro Prompt

Use this prompt to generate a standalone HTML product introduction page about popular games in the Pixel Terminal UI style.

```text
Use the pixel-terminal-ui style to create a standalone responsive HTML page introducing popular games.

Subject: 热门游戏介绍 / Hot Games Radar.

The page should feel like a dark macOS-native terminal HUD mounted to the top of the operating system. The first viewport should show a black top-centered notch/status pill, a pixel terminal hero title, a live game radar panel, and real game cards with cover images or recognizable media. Use a compact dashboard structure instead of a generic marketing landing page.

Design requirements:
- dark black/near-black background with subtle grain, scanline, ASCII, or dither texture
- pixel/mono title typography, system sans for readable body text
- semantic colors only: green for online/ready, blue for running/trending, orange for hot/attention, cyan for discovery, red for warning
- black glass-like panels with thin translucent borders and soft shadows
- dense game cards with genre, platform, popularity, status, and short description
- terminal-style side panel showing scan logs, rankings, or recommendation output
- compact buttons and chips with keyboard-hint styling
- no decorative gradient blobs, no generic SaaS bento page, no beige palette, no heavy neon cyberpunk

Content should include 6 popular games. Example set:
- Counter-Strike 2
- Dota 2
- PUBG: Battlegrounds
- Apex Legends
- Rust
- Grand Theft Auto V

Interactions:
- clicking a game card updates the terminal detail panel
- title or status text can use subtle ASCII scramble animation
- hover states should be crisp and restrained
- provide reduced-motion fallback

Responsive requirements:
- no horizontal overflow on mobile or desktop
- text must fit inside cards and buttons
- hero-scale type only in hero area; panels use compact headings
- images must have stable aspect ratios
```

## Layout Recipe

```text
Top notch pill
Hero title + subtitle
Primary game radar grid
Focused game terminal detail panel
Trending queue / scan logs
Comparison or recommendation strip
```

## CSS Tokens To Start From

```css
:root {
  --pt-bg: #111111;
  --pt-bg-deep: #050505;
  --pt-surface: #151518;
  --pt-ink: #000000;
  --pt-panel: rgba(14, 14, 16, 0.94);
  --pt-border: rgba(255, 255, 255, 0.10);
  --pt-text: #e5e5e5;
  --pt-text-soft: rgba(255, 255, 255, 0.72);
  --pt-text-dim: rgba(255, 255, 255, 0.42);
  --pt-orange: #d97757;
  --pt-green: #22c55e;
  --pt-blue: #3b82f6;
  --pt-cyan: #06b6d4;
  --pt-red: #f87171;
}
```
