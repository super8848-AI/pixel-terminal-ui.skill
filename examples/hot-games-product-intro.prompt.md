# Hot Games Product Intro Prompt

Use this prompt to generate a standalone HTML product introduction page about popular games in the Pixel Terminal UI style.

```text
Use the pixel-terminal-ui style to create a standalone responsive HTML page introducing popular games.

Subject: 热门游戏介绍 / Hot Games Radar.

The page should feel like a dark macOS-native terminal HUD mounted to the top of the operating system. The first viewport should show a black top-centered notch/status pill, a pixel terminal hero title, a live game radar panel, and real game cards with cover images or recognizable media. Use a compact dashboard structure instead of a generic marketing landing page.

Design requirements:
- dark black/near-black background with subtle top god-rays, 128px grain, optional 4x4 ordered dither, and binary/ASCII scatter
- binary scatter should use `0 1 + - * : .`, fade from a corner or behind the hero, and never cover readable text
- pixel/mono title typography; for Chinese titles prefer `Zpix`, `Fusion Pixel`, `Ark Pixel`, or `Noto Sans Mono CJK SC`
- use pixel Chinese only for headings and short labels; body paragraphs should use system Chinese fonts for readability
- avoid text-shadow/glow on Chinese pixel headings so the glyphs stay crisp
- binary scatter can glow cyan around the pointer by increasing alpha for characters near the mouse position
- semantic colors only: #d97757 orange for hot/product attention, #22c55e green for online/ready, #3b82f6 blue for running/trending, #06b6d4 cyan for discovery/questions, #a855f7 purple for exploration, red for warning
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
