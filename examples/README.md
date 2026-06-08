# Examples

This directory contains example prompts and implementation directions for reusing the Pixel Terminal UI skill.

## Available Examples

- `hot-games-product-intro.prompt.md`: prompt and layout recipe for a popular-games product introduction page.

## Recommended Output Shape

For product intro pages, avoid a generic SaaS landing page. Build a real first-screen interface:

- top-centered black notch/status pill
- compact terminal or HUD surface
- dense game/product rows
- semantic status colors
- image-backed content cards only when they help the subject feel real
- subtle grain, ASCII scatter, and scanline texture

## Verification

For HTML or frontend output, verify at least:

- desktop viewport has no horizontal overflow
- mobile viewport has no horizontal overflow
- images load successfully
- text stays inside buttons, cards, and panels
- decorative terminal effects do not cover readable content
