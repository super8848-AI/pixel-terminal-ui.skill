# Core Prompt

Use this prompt when asking a designer, image model, Figma agent, or frontend agent to apply the style.

```text
Design a dark pixel terminal interface for a real product surface. The UI should feel like a compact control surface mounted to the product: a pure-black top status pill, compact overlay, or expandable control bar, with dense terminal rows, code/diff context, keyboard hints, semantic live states, and crisp pixel icons. Use a near-black background with pale top god-rays, optional 4x4 ordered dither, 128px grain noise, and sparse binary/ASCII scatter using `0 1 + - * : .`; fade the scatter from a corner or behind the hero so it never covers readable text, and optionally make nearby characters glow cyan on pointer movement. Use pixel/monospace display typography: `Zpix` for Chinese headings, plus `Geist Pixel Square`, `Departure Mono`, `Press Start 2P`, and `JetBrains Mono` for Latin/code. For Chinese headings prefer `Zpix` before normal system fonts; use pixel Chinese only for headings, short labels, and chips, while paragraph body copy should use system Chinese fonts for readability. Avoid glow/blur shadows on Chinese pixel headlines because they make glyphs fuzzy. Use color only as state or tool identity: text `#e5e5e5`, orange `#d97757` for product or attention, green `#22c55e`/`#4ade80` for done or approved states, blue `#3b82f6`/`#60a5fa` for running states, cyan `#06b6d4` for questions and scatter glow, purple `#a855f7` for exploration, yellow `#f59e0b` for alternate tools, red only for errors. The product should look functional first, not like a generic SaaS landing page. Avoid decorative gradient blobs, heavy neon cyberpunk, beige palettes, oversized cards, and copied branded assets. Prioritize a real usable dashboard/control panel over marketing composition.
```

## Chinese Short Prompt

```text
做一个暗黑像素终端风控制界面：顶部可以是纯黑状态 pill、紧凑悬浮条，或可展开的控制面板。整体是紧凑、状态驱动、终端原生的产品气质，使用像素/等宽字体、二进制 01 背景、ASCII 扰动、轻微 128px 颗粒、顶部 god-ray 光束、可选 4x4 有序抖动、黑色实体面板、细边框和柔和阴影。中文标题优先用 Zpix 这类真像素中文字体，正文不要用像素中文，正文回退系统中文字体保证清晰；中文像素标题不要加发光/模糊阴影。01 背景可以做成鼠标附近青色发光的 canvas 雷达效果。颜色只表达状态：#d97757 橙=产品/注意，#22c55e 绿=完成，#3b82f6 蓝=运行，#06b6d4 青=提问/二进制发光，#a855f7 紫=探索，#f59e0b 黄=备用工具身份，红=错误。避免通用 SaaS 卡片、霓虹赛博、渐变光球和营销页感，优先做可用的控制台/仪表盘。
```
