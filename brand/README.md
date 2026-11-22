# sealctl brand

## Mark

<img src="mark.svg" width="64" alt="sealctl mark"> <img src="app-icon.svg" width="64" alt="sealctl app icon">

**Box shield:** a terminal window holding a shield, holding the prompt. The command runs inside the protection, on your own machine.

| File | Use |
| --- | --- |
| `mark.svg` | The mark on light backgrounds (sealing wax `#b4232c`) |
| `mark-dark.svg` | The mark on dark backgrounds (`#ff5c63`) |
| `mark-mono.svg` | One colour, ink `#1a2133`, for print and places that allow no colour |
| `app-icon.svg` | App icon, 1024 px, full bleed; the stores round the corners. The window is dropped because the icon tile plays its part |
| `avatar.png` | 512 px avatar for GitHub and other profiles |
| `social-preview.svg`, `.png` | 1280 × 640 link preview |

- Smallest size: 16 px. Below 24 px, prefer the app-icon glyph (shield and prompt) if the prompt gets lost.
- Clear space around the mark: a quarter of its width.
- Don't recolour, outline, add gradients, rotate or put the mark on photos.

## Wordmark

`sealctl` in lower case, set in the system monospace (`ui-monospace`, SF Mono, JetBrains Mono, Menlo), weight 600–650, letter spacing −0.03em. The mark sits to its left, its height about 1.1× the cap height.

## Colour

One accent, sealing wax, on cool neutrals: white and blue-grey surfaces, navy ink. No cream or beige, no gradients. All values are in `tokens.css`.

| Token | Light | Dark |
| --- | --- | --- |
| Paper (background) | `#ffffff` | `#0e121a` |
| Surface (cards) | `#f6f7f9` | `#151a24` |
| Ink (text) | `#1a2133` | `#eef0f5` |
| Accent | `#b4232c` | `#ff5c63` |
| Text on accent | `#ffffff` | `#12151c` |

Contrast: accent text on paper 6.5 : 1 (light) and 6.2 : 1 (dark); button labels on the accent 6.5 : 1 and 6.1 : 1; muted text on `surface-2` 5.0 : 1 and 5.8 : 1. All pass WCAG AA.

Semantic colours (passing tests, warnings) stay separate from the accent: green means success, never the brand.

## Type and layout

- Text: the system sans (`ui-sans-serif`, `system-ui`). Code, commands, the 24 words' fingerprints and the wordmark: the system monospace.
- 12 px corners on cards, soft shadows, light and dark themes from the same tokens.
- Show the real product (a terminal and the phone's approval screen) rather than illustrations.

## Voice

Plain and specific: say what happens ("your phone asks, you tap Allow, the key goes into that one command"). Same words everywhere: Locked, Open, Waiting, One tap, Places. Only claims that are true and checkable: no user counts, testimonials, logos of customers or certifications we don't hold.
