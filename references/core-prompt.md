# Core Prompt

Use this prompt when asking a designer, image model, Figma agent, or frontend agent to apply the style.

```text
Design a dark macOS-native pixel terminal interface for a developer workflow product, inspired by the Vibe Island website without copying its assets. The UI should feel like a compact control surface mounted to the operating system: a pure-black notch/top-bar pill that can expand into a notification or session panel, with dense terminal rows, code/diff context, keyboard hints, semantic live states, and crisp pixel icons. Use a near-black background with pale top god-rays, optional 4x4 ordered dither, 128px grain noise, and sparse binary/ASCII scatter using `0 1 + - * : .`; fade the scatter from a corner or behind the hero so it never covers readable text, and optionally make nearby characters glow cyan on pointer movement. Use pixel/monospace display typography: `Zpix` for Chinese headings, plus `Geist Pixel Square`, `Departure Mono`, `Press Start 2P`, and `JetBrains Mono` for Latin/code. For Chinese headings prefer `Zpix` before normal system fonts; use pixel Chinese only for headings, short labels, and chips, while paragraph body copy should use system Chinese fonts for readability. Avoid glow/blur shadows on Chinese pixel headlines because they make glyphs fuzzy. Use color only as state or tool identity: text `#e5e5e5`, orange `#d97757` for product/Claude/attention, green `#22c55e`/`#4ade80` for done/Codex, blue `#3b82f6`/`#60a5fa` for running/Gemini, cyan `#06b6d4` for questions and scatter glow, purple `#a855f7` for exploration/Cursor, yellow `#f59e0b` for alternate tools, red only for errors. The product should look functional first, not like a generic SaaS landing page. Avoid decorative gradient blobs, heavy neon cyberpunk, beige palettes, oversized cards, and copied Apple/Vibe Island assets. Prioritize a real usable dashboard/control panel over marketing composition.
```

## Chinese Short Prompt

```text
做一个参考 Vibe Island 官网气质但不复制素材的暗黑像素终端风 macOS 原生控制界面：像挂在刘海/顶部栏里的纯黑状态 pill，可展开成通知或会话面板。整体是开发者工具气质，紧凑、状态驱动、终端原生，使用像素/等宽字体、二进制 01 背景、ASCII 扰动、轻微 128px 颗粒、顶部 god-ray 光束、可选 4x4 有序抖动、黑色实体面板、细边框和柔和阴影。中文标题优先用 Zpix 这类真像素中文字体，正文不要用像素中文，正文回退系统中文字体保证清晰；中文像素标题不要加发光/模糊阴影。01 背景可以做成鼠标附近青色发光的 canvas 雷达效果。颜色只表达状态：#d97757 橙=产品/Claude/注意，#22c55e 绿=完成/Codex，#3b82f6 蓝=运行/Gemini，#06b6d4 青=提问/二进制发光，#a855f7 紫=探索/Cursor，#f59e0b 黄=备用工具身份，红=错误。避免通用 SaaS 卡片、霓虹赛博、渐变光球和营销页感，优先做可用的控制台/仪表盘。
```
