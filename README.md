# draftvolt-panels

Per-panel "passport" pages for DRAFTVOLT installations. Each completed
distribution board gets a small static page reachable through a QR code
sticker placed inside the box. The page records the as-built configuration
of the panel — incoming protection, branch schedule, operating notes — for
the householder and for any electrician who opens the box later.

## URL convention

```
https://draftvolt.github.io/draftvolt-panels/p/<slug>/
```

Slugs are unguessable, generated per-panel, and printed only on the
sticker inside the box. The root landing page does not enumerate them.

## Layout

```
draftvolt-panels/
├── index.html              # discreet root landing (no listing)
├── assets/                 # logo, favicon — shared across passports
└── p/
    └── <slug>/
        ├── index.html      # the passport page
        └── panel.jpg       # panel render / photo
```

## Adding a new panel

1. Generate a fresh slug (e.g. `dv-XXXXX`).
2. Copy `p/dv-7k2m9/` to `p/<new-slug>/` as a starting template.
3. Replace `panel.jpg` with the new panel's render.
4. Edit the passport's identification block, incoming-protection specs,
   and branch schedule.
5. Update `<title>` and the slug printed in the masthead and colophon.
6. Generate the QR code pointing at the live URL. Print, place inside
   the box.

## Hosting

GitHub Pages, served from `main` branch root. Public, but practical
discoverability is gated by the slug. If a customer asks for stronger
privacy, the page can be moved to a separate slug and the old one
deleted — the QR sticker is the only canonical pointer.
