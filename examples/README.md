# Examples

This directory contains example prompts and implementation directions for reusing the Pixel Terminal UI skill in real product surfaces.

## Available Examples

- `hot-games-product-intro.prompt.md`: prompt and layout recipe for a popular-games product introduction page.

## Recommended Output Shape

For product intro pages, avoid a generic SaaS landing page. Build a real first-screen interface:

- top-centered black status pill or compact control surface
- compact terminal or HUD surface
- dense game/product rows
- semantic status colors
- pixel Chinese font stack when Chinese content is present
- image-backed content cards only when they help the subject feel real
- subtle god-ray, 128px grain, 4x4 dither, and binary `0 1 + - * : .` scatter

## How To Reuse

- Start from a concrete workflow or content structure, not abstract mood words
- Map content into status pills, terminal rows, compact panels, and HUD blocks
- Keep decorative texture behind the product layer so the UI still reads clearly
- Reuse the same semantic color system across pages to keep the style coherent

## Verification

For HTML or frontend output, verify at least:

- desktop viewport has no horizontal overflow
- mobile viewport has no horizontal overflow
- images load successfully
- text stays inside buttons, cards, and panels
- decorative terminal effects do not cover readable content
