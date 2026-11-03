# Grok Imagine Video + Image · Brand guide

**A scene starts with a sentence.** A cinematic identity for this independent
Python client and OpenClaw skill, not an official identity for xAI or OpenClaw.
The runtime, API methods, and skill behavior are unchanged by the branding work.

## Visual system

| Token | Value | Role |
|---|---|---|
| Charcoal | `#111314` | Canvas |
| Bone | `#EEEAE1` | Main text |
| Amber | `#F4B45E` | Emphasis, connectors, links |
| Silver | `#B3B6B6` | Supporting text |
| Rule | `#454A4B` | Dividers |

Condensed display type creates a production-title feel. Supporting text uses
Avenir Next or a system fallback; code and running labels use a local monospace
stack. No remote fonts, scripts, or build dependencies are needed. The bracketed
play mark identifies this community package, not the API provider.

## Asset inventory

| Asset | Purpose | Source |
|---|---|---|
| `banner.png` | README header, 1600 × 800 | Browser render of `banner.html` |
| `banner.html`, `brand.css` | Editable banner copy, layout, and tokens | HTML/CSS |
| `images/mark.svg` | Community package mark | Editable SVG |
| `images/cinematic-hero.webp` | Three-frame cinematic concept | AI-generated, locally optimized |
| `images/video-workflow.png` | Describe → submit → poll → save | AI-generated infographic |
| `images/capability-map.png` | Five image/video API paths | AI-generated infographic |
| `brand.html` | Responsive visual preview and text explanations | HTML/CSS |

These images are conceptual illustrations, not samples captured from Grok
Imagine, videos rendered by the client, or guaranteed outputs. No live API
generation was required to produce the documentation. The diagrams describe the
checked-in client methods, not a promise that provider limits stay unchanged.

## Preview

Open `docs/brand.html` directly in a browser. All files load locally. The
infographic explanations also appear as text in the README and visual preview
for screen readers and small screens.

## Regenerate the banner

From the repository root, with `agent-browser` available:

```bash
root="$(pwd)"
export AGENT_BROWSER_SESSION="${AGENT_BROWSER_SESSION:-$(agent-browser session id --scope worktree --prefix grok-brand)}"
agent-browser set viewport 1600 800
agent-browser open "file://$root/docs/banner.html"
agent-browser wait --fn 'Array.from(document.images).every(img => img.complete && img.naturalWidth > 0)'
agent-browser screenshot "$root/docs/banner.png"
agent-browser close
```

The PNG preserves the rendered layout across GitHub clients. Font fallback can
change a regenerated banner on a different operating system. The infographics
are frozen image assets; changing their text requires editing or regenerating
the images and checking them against `scripts/grok_video_api.py`.
