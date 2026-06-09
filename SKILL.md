---
name: pixel-terminal-ui
description: Create or adapt product interfaces in a dark pixel-terminal aesthetic with compact status surfaces, terminal dashboards, AI agent monitors, developer tools, command centers, HUDs, permission panels, and live overlays. Use when the user asks for "像素终端", "pixel terminal", "notch UI", "dark terminal UI", "AI agent dashboard", or wants a product to reuse this design language.
---

# Pixel Terminal UI

Use this skill to design and implement interfaces that feel like a native macOS control surface mixed with a retro terminal HUD: dark, compact, pixel-aware, state-driven, and developer-native.

Use it when the request needs a visible product surface, not just styling notes: dashboards, overlays, monitors, approval flows, launch pages, or compact tool UIs.

## Workflow

1. Treat the product surface as a live control panel, not a marketing page.
2. Start from real workflow states: idle, running, waiting, asking, approval, done, error.
3. Use black/near-black as the primary material, with soft glass only for depth.
4. Use pixel or mono display typography for headings/status. For Chinese UI, prefer pixel-capable Chinese fonts such as `Zpix`, `Fusion Pixel`, `Ark Pixel`, or `Noto Sans Mono CJK SC` before falling back to system sans.
5. Keep colors semantic: green for ready/done, blue for running, orange for permission/attention, cyan for questions, purple only for exploration/tool identity.
6. Design compact repeated rows, pills, terminal windows, status glyphs, and notification bodies before decorative sections.
7. Add texture carefully: sparse `0 1 + - * : .` binary scatter, 128px grain, subtle god-ray light, optional 4x4 ordered dithering, and screen fade masks.
8. Add motion as state feedback: breathing dots, ASCII scramble text, waveform bars, soft expansion from a pill, and cross-fades.
9. Verify that the interface remains usable without the novelty layer.
10. Keep the output portable so the same design language can be reused across tools, frameworks, and agents.

## Reference Files

- Read `references/style-guide.md` for the visual grammar, palette, typography, and do/don't rules.
- Read `references/component-patterns.md` when implementing React/HTML/CSS components.
- Read `references/core-prompt.md` when the user wants a prompt for a designer, image model, Figma handoff, or another agent.

## Implementation Bias

- For frontend work, create the actual usable interface first. Avoid standalone landing pages unless requested.
- Prefer a single primary black surface that morphs or expands, especially for notch/status/notification UI.
- Keep cards shallow and functional. Repeated rows are better than large decorative cards for developer tools.
- Use monospaced code snippets and terminal window metaphors only when they clarify the workflow.
- Include pixel grain, dither, scan/noise, and ASCII scatter as subtle texture, not as the main content.
- Do not copy branded assets directly. Reuse the design principles: pill morphology, compact state surface, semantic status, and terminal-native interaction.
