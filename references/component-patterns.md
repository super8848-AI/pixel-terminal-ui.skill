# Component Patterns

## Base CSS

```css
.pt-shell {
  min-height: 100vh;
  color: var(--pt-text);
  background:
    radial-gradient(ellipse at 50% 0%, rgba(45, 42, 55, 0.38), transparent 55%),
    radial-gradient(ellipse at 80% 100%, rgba(35, 28, 22, 0.22), transparent 50%),
    var(--pt-bg);
  font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "Segoe UI", system-ui, sans-serif;
}

.pt-noise::before {
  content: "";
  position: fixed;
  inset: 0;
  pointer-events: none;
  opacity: 0.13;
  mix-blend-mode: overlay;
  background-image:
    repeating-radial-gradient(circle at 20% 30%, rgba(255,255,255,.08) 0 1px, transparent 1px 3px);
}

.pt-pixel-title {
  font-family: "Departure Mono", "Geist Pixel Square", "JetBrains Mono", ui-monospace, monospace;
  letter-spacing: .04em;
  -webkit-font-smoothing: none;
  image-rendering: pixelated;
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
  font: 500 10px/1.2 "JetBrains Mono", ui-monospace, monospace;
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
