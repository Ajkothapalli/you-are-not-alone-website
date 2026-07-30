# soulyap — Neo-Brutal Design Language

## Principles
- **Raw structure**: visible borders, offset shadows, no gradients
- **Intentional roughness**: slight rotations, bold strokes, high contrast
- **Typographic weight**: Display font (Plus Jakarta Sans 800) carries visual hierarchy
- **Color as signal**: accent colors are functional — ember = warmth, twilight = clarity, rose = vulnerability

---

## Shadow system
| Level | Value |
|---|---|
| Card (large) | `7px 7px 0 var(--you)` |
| Card hover | `3px 3px 0 var(--you)` |
| UI element | `5px 5px 0 rgba(0,0,0,.55)` |
| Small badge | `2px 2px 0 rgba(0,0,0,.35)` |

## Border system
- Cards: `2.5px solid var(--paper)`
- UI buttons: `3px solid #000`
- Pills/badges: `1.5px solid currentColor`
- Corner radius: cards `22px`, buttons `16px`, pills `6px`, tags `5px`

---

## Iconography — Card Graphics

Each confession card variant carries a large, stroke-only, 45°-rotated background graphic clipped to the card's bottom-right corner. Opacity: `0.18`. Color: `var(--you)` (the card's accent).

### Rules
- Stroke-only, no fill (or fill="none")
- Stroke width: 6–8px
- Size: 140×140px rendered
- Position: `bottom: -24px; right: -24px; transform: rotate(45deg)`
- Card must have `overflow: hidden`
- `pointer-events: none`

### Icon set

#### 1. Speech Bubble (`#ember` / orange)
Two speech bubble rectangles — confession, voice, saying the thing.
```svg
<svg viewBox="0 0 110 90" fill="none" xmlns="http://www.w3.org/2000/svg">
  <rect x="5" y="5" width="46" height="34" rx="10" stroke="currentColor" stroke-width="7"/>
  <path d="M12 39 L22 52" stroke="currentColor" stroke-width="7" stroke-linecap="round"/>
  <rect x="59" y="18" width="46" height="34" rx="10" stroke="currentColor" stroke-width="7"/>
  <path d="M66 52 L76 65" stroke="currentColor" stroke-width="7" stroke-linecap="round"/>
</svg>
```

#### 2. Infinity (`#twilight` / cyan)
Infinity loop — you are never the only one, it keeps going.
```svg
<svg viewBox="0 0 120 60" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M60 30 C60 30 72 8 90 8 C108 8 116 18 116 30 C116 42 108 52 90 52 C72 52 48 8 30 8 C12 8 4 18 4 30 C4 42 12 52 30 52 C48 52 60 30 60 30Z"
    stroke="currentColor" stroke-width="7" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
```

#### 3. Diamond (`#rose` / pink)
Diamond / rhombus — the rare, precious moment of being truly seen.
```svg
<svg viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path d="M40 6 L74 40 L40 74 L6 40 Z" stroke="currentColor" stroke-width="7" stroke-linejoin="round"/>
  <path d="M40 22 L58 40 L40 58 L22 40 Z" stroke="currentColor" stroke-width="4" stroke-linejoin="round"/>
</svg>
```

---

## Palette
```
--bg:      #08121A   background
--surface: #0F1E28   card surface
--paper:   #F3EEE8   primary text / border
--dim:     #7A9EAD   muted text

ember:     #F59E42   warmth, courage
twilight:  #22D3EE   clarity, calm
rose:      #F472B6   vulnerability, love
cool:      #22D3EE
mint:      #34D399
gold:      #FBBF24
```

## Typography
| Role | Font | Weight | Size |
|---|---|---|---|
| Display / heading | Plus Jakarta Sans | 800 | clamp(46px, 10vw, 108px) |
| Label / pill | Plus Jakarta Sans | 700–800 | 10–13px, 0.14em tracking |
| Body | Inter | 500 | 14–16px |
| Confession | Fraunces | 400 | 18–19px |
| Italic accent | Fraunces Italic | 400 | contextual |
