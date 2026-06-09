# Component Patterns

## Base CSS

```css
@font-face {
  font-family: "Zpix";
  font-style: normal;
  font-display: swap;
  font-weight: 400;
  src: url("https://cdn.jsdelivr.net/gh/SolidZORO/zpix-pixel-font@master/website/zpix.woff2") format("woff2");
}

:root {
  --pt-bg: #111111;
  --pt-bg-deep: #050505;
  --pt-bg-soft: #1a1a1a;
  --pt-surface: #151518;
  --pt-ink: #000000;
  --pt-terminal: #1e1e1e;
  --pt-panel: rgba(14, 14, 16, 0.94);
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
  --pt-spring: cubic-bezier(.175, .885, .32, 1.1);
  --pt-font-pixel: "Zpix", "Geist Pixel Square", "Departure Mono", "Press Start 2P", "Fusion Pixel 12px Monospaced SC", "Fusion Pixel", "Ark Pixel 12px zh_cn", "Noto Sans Mono CJK SC", ui-monospace, monospace;
  --pt-font-mono: "JetBrains Mono", "SF Mono", ui-monospace, monospace;
  --pt-font-sans: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Segoe UI", "PingFang SC", "Noto Sans CJK SC", system-ui, sans-serif;
}

.pt-shell {
  min-height: 100vh;
  color: var(--pt-text);
  background:
    radial-gradient(ellipse at 50% -10%, rgba(255, 255, 255, .12), transparent 34%),
    radial-gradient(ellipse at 50% 0%, rgba(45, 42, 55, 0.34), transparent 55%),
    radial-gradient(ellipse at 80% 100%, rgba(217, 119, 87, 0.14), transparent 48%),
    var(--pt-bg);
  font-family: var(--pt-font-sans);
}

.pt-shell::before {
  content: "";
  position: fixed;
  inset: 0;
  z-index: 1;
  pointer-events: none;
  opacity: 0.13;
  mix-blend-mode: overlay;
  background-image:
    linear-gradient(rgba(255,255,255,.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,.035) 1px, transparent 1px),
    repeating-radial-gradient(circle at 22% 32%, rgba(255,255,255,.08) 0 1px, transparent 1px 4px);
  background-size: 100% 4px, 4px 100%, 128px 128px;
}

.pt-shell::after {
  content: "0101 +++ ::: AGENT SIGNALS // PIXEL TERMINAL //";
  position: fixed;
  inset: 84px 0 auto;
  z-index: 0;
  height: 360px;
  overflow: hidden;
  color: rgba(255,255,255,.045);
  font: 10px/1.9 var(--pt-font-mono);
  letter-spacing: .35em;
  white-space: pre-wrap;
  text-align: center;
  pointer-events: none;
  mask-image: radial-gradient(ellipse at 50% 35%, black 0 18%, transparent 68%);
}

.pt-pixel-title {
  font-family: var(--pt-font-pixel);
  letter-spacing: 0;
  -webkit-font-smoothing: none;
  -moz-osx-font-smoothing: unset;
  font-synthesis: none;
  text-rendering: geometricPrecision;
  image-rendering: pixelated;
  text-shadow: none;
}

.pt-body-copy {
  font-family: var(--pt-font-sans);
  letter-spacing: 0;
  line-height: 1.65;
}

.pt-pill {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  height: 34px;
  padding: 0 16px;
  color: var(--pt-text);
  background: var(--pt-ink);
  border-radius: 0 0 16px 16px;
  box-shadow: 0 2px 10px rgba(0,0,0,.72), 0 12px 32px rgba(0,0,0,.38);
  transition: width .5s var(--pt-spring), height .5s var(--pt-spring), border-radius .4s ease-out;
}

.pt-notch {
  position: relative;
  width: 240px;
  height: 36px;
  background: #000;
  border-radius: 0 0 14px 14px;
  box-shadow: 0 2px 8px rgba(0,0,0,.6), 0 8px 24px rgba(0,0,0,.3);
}

.pt-notch::before,
.pt-notch::after {
  content: "";
  position: absolute;
  top: 0;
  width: 13px;
  height: 25px;
  pointer-events: none;
}

.pt-notch::before {
  left: -13px;
  border-top-right-radius: 6px;
  box-shadow: 5px 0 #000;
}

.pt-notch::after {
  right: -13px;
  border-top-left-radius: 6px;
  box-shadow: -5px 0 #000;
}

.pt-panel {
  background: rgba(10, 10, 12, .96);
  border: 1px solid var(--pt-border);
  box-shadow: 0 20px 80px rgba(0,0,0,.58), inset 0 1px rgba(255,255,255,.08);
  backdrop-filter: blur(18px) saturate(140%);
}

.pt-row {
  display: grid;
  grid-template-columns: auto minmax(0, 1fr) auto;
  gap: 10px;
  align-items: center;
  padding: 8px 10px;
  border-radius: 7px;
}

.pt-row:hover { background: rgba(255,255,255,.07); }

.pt-chip {
  padding: 2px 6px;
  border-radius: 5px;
  color: var(--pt-text-soft);
  background: rgba(255,255,255,.10);
  font: 500 10px/1.2 var(--pt-font-mono);
}

.pt-terminal {
  overflow: hidden;
  border-radius: 10px;
  background: rgba(30,30,30,.86);
  border: 1px solid rgba(255,255,255,.10);
  box-shadow: 0 14px 38px rgba(0,0,0,.48);
  backdrop-filter: blur(20px);
}

.pt-terminal-bar {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 8px 10px;
  border-bottom: 1px solid rgba(255,255,255,.06);
  background: rgba(255,255,255,.06);
}

.pt-dot { width: 8px; height: 8px; border-radius: 50%; }
.pt-dot.red { background: #ff5f56; }
.pt-dot.yellow { background: #ffbd2e; }
.pt-dot.green { background: #27c93f; }

.pt-mac-mask {
  -webkit-mask-image: linear-gradient(to bottom, black 70%, transparent 95%);
  mask-image: linear-gradient(to bottom, black 70%, transparent 95%);
}
```

## Binary Scatter Canvas

Use this for hero or pricing-card background texture: sparse `0 1 + - * : .` characters, a corner fade, and a cyan proximity glow. The glow is driven by mouse distance: characters near the pointer get higher alpha and a stronger cyan mix.

```html
<canvas class="pt-binary-scatter" aria-hidden="true"></canvas>
```

```css
.pt-binary-scatter {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  opacity: .9;
  mask-image: radial-gradient(circle at 100% 0%, black, transparent 62%);
}
```

```js
export function mountBinaryScatter(canvas) {
  const ctx = canvas.getContext("2d");
  if (!ctx) return;
  const chars = ["0", "1", "+", "-", "*", ":", "."];
  const cyan = [6, 182, 212];
  let cell = window.innerWidth < 768 ? 14 : 10;
  let cols = 0, rows = 0, width = 0, height = 0, grid = [];
  let mx = -999, my = -999;

  function resize() {
    const box = canvas.parentElement || canvas;
    width = box.offsetWidth;
    height = box.offsetHeight;
    const dpr = Math.min(window.devicePixelRatio || 1, 2);
    canvas.width = width * dpr;
    canvas.height = height * dpr;
    canvas.style.width = width + "px";
    canvas.style.height = height + "px";
    ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
    cell = window.innerWidth < 768 ? 14 : 10;
    cols = Math.ceil(width / cell);
    rows = Math.ceil(height / cell);
    grid = Array.from({ length: rows }, () =>
      Array.from({ length: cols }, () => chars[(Math.random() * chars.length) | 0])
    );
    draw();
  }

  function draw() {
    ctx.clearRect(0, 0, width, height);
    ctx.font = `${Math.floor(cell * .65)}px "JetBrains Mono", monospace`;
    ctx.textAlign = "center";
    ctx.textBaseline = "middle";
    const maxDist = Math.sqrt(width * width + height * height) * .6;
    for (let r = 0; r < rows; r++) {
      for (let c = 0; c < cols; c++) {
        const x = c * cell + cell / 2;
        const y = r * cell + cell / 2;
        const dist = Math.hypot(x - width, y);
        const fade = Math.max(0, 1 - dist / maxDist);
        const glow = Math.max(0, 1 - Math.hypot(x - mx, y - my) / 80);
        const alpha = fade * .30 + glow * .50;
        if (alpha < .02) continue;
        const mix = Math.max(0, 1 - dist / (maxDist * .5));
        const red = Math.round(255 - (255 - cyan[0]) * mix);
        const green = Math.round(255 - (255 - cyan[1]) * mix);
        const blue = Math.round(255 - (255 - cyan[2]) * mix);
        ctx.fillStyle = `rgba(${red},${green},${blue},${alpha.toFixed(3)})`;
        ctx.fillText(grid[r][c], x, y);
      }
    }
  }

  canvas.addEventListener("pointermove", (event) => {
    const rect = canvas.getBoundingClientRect();
    mx = event.clientX - rect.left;
    my = event.clientY - rect.top;
    draw();
  });
  window.addEventListener("resize", resize);
  resize();
}
```

## God-Ray and Grain Layers

For a lightweight CSS-only approximation, use a pale top light plus a generated noise tile. Keep opacity low.

```css
.pt-godray {
  position: fixed;
  inset: 0;
  pointer-events: none;
  background:
    conic-gradient(from 180deg at 50% -20%, transparent 0 22deg, rgba(255,255,255,.12) 34deg, transparent 46deg 100deg, rgba(255,255,255,.08) 118deg, transparent 132deg),
    radial-gradient(ellipse at 50% -10%, rgba(255,255,255,.16), transparent 42%);
  opacity: .7;
  mix-blend-mode: screen;
}

.pt-grain {
  position: fixed;
  inset: 0;
  pointer-events: none;
  opacity: .12;
  mix-blend-mode: overlay;
}
```

```js
export function mountGrain(el) {
  const size = 128;
  const canvas = document.createElement("canvas");
  canvas.width = size;
  canvas.height = size;
  const ctx = canvas.getContext("2d");
  if (!ctx) return;
  const image = ctx.createImageData(size, size);
  for (let i = 0; i < image.data.length; i += 4) {
    const value = (Math.random() * 60) | 0;
    image.data[i] = value;
    image.data[i + 1] = value;
    image.data[i + 2] = value;
    image.data[i + 3] = 255;
  }
  ctx.putImageData(image, 0, 0);
  el.style.backgroundImage = `url(${canvas.toDataURL()})`;
  el.style.backgroundSize = `${size}px ${size}px`;
}
```

## React Status Pill

```tsx
type Phase = "idle" | "running" | "approval" | "question" | "done" | "error";

const phaseColor: Record<Phase, string> = {
  idle: "var(--pt-text-dim)",
  running: "var(--pt-blue)",
  approval: "var(--pt-alert)",
  question: "var(--pt-cyan)",
  done: "var(--pt-green)",
  error: "var(--pt-red)",
};

export function PixelStatusPill({
  phase,
  label,
  count,
}: {
  phase: Phase;
  label: string;
  count?: number;
}) {
  return (
    <div className="pt-pill" data-phase={phase}>
      <WaveGlyph phase={phase} color={phaseColor[phase]} />
      <span className="pt-pixel-title" style={{ fontSize: 12 }}>{label}</span>
      {typeof count === "number" && <span className="pt-chip">x{count}</span>}
    </div>
  );
}

function WaveGlyph({ phase, color }: { phase: Phase; color: string }) {
  const running = phase === "running";
  const waiting = phase === "approval" || phase === "question";
  return (
    <span aria-hidden style={{ display: "inline-flex", gap: 3, alignItems: "center", height: 18 }}>
      {[0, 1, 2].map((i) => (
        <span
          key={i}
          style={{
            width: 3,
            height: running ? [7, 14, 9][i] : waiting ? [12, 0, 12][i] : [4, 6, 4][i],
            borderRadius: 2,
            background: color,
            opacity: waiting && i === 1 ? 0 : 0.9,
            animation: running ? `pt-wave .9s ease-in-out ${i * .12}s infinite` : undefined,
          }}
        />
      ))}
    </span>
  );
}
```

```css
@keyframes pt-wave {
  0%, 100% { transform: scaleY(.55); opacity: .65; }
  50% { transform: scaleY(1.2); opacity: 1; }
}
```

## ASCII Scramble Text

```js
export function scrambleText(el, next, color = "#e5e5e5") {
  const chars = "01+-*:.";
  const from = el.textContent || "";
  const length = Math.max(from.length, next.length);
  el.style.color = color;
  el.textContent = "";
  const spans = Array.from({ length }, (_, i) => {
    const span = document.createElement("span");
    span.textContent = from[i] || " ";
    el.appendChild(span);
    return span;
  });
  spans.forEach((span, i) => {
    let ticks = 4;
    const settle = () => {
      if (ticks-- > 0) {
        span.textContent = chars[(Math.random() * chars.length) | 0];
        setTimeout(settle, 40);
      } else {
        span.textContent = next[i] || "";
      }
    };
    setTimeout(settle, i * 30);
  });
}
```

## Permission Card Content Pattern

- Header: small status dot + "Permission Request".
- Tool row: warning/icon + tool name + target path.
- Context: mini diff, command preview, or affected resource.
- Actions: Deny / Allow / Always Allow with keyboard hints.
- Do not over-explain. The UI is for fast decision-making.
