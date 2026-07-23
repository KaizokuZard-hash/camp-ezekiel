# Camp Ezekiel 2026 Website — Project Context

Static one-page site for **Camp Ezekiel** (July 31 – Aug 2, 2026), a camp run by
Forward In Faith Ministries International — USA Youth & Young Adults, **South Region**.
One camp, two tracks: **Youth** and **Young Adults**.

## Architecture

- Plain static site: `index.html` (all CSS/JS inline) + image assets. No build step, no dependencies.
- `logo.png` — round camp logo (used in nav, hero badge, footer, favicon).
- `logo-white.png` — white version of the logo (currently **unused**; owner declined a hero swap).
- `icons/` — pixel-art icons (calendar, location, money, phone → Details cards; shield, clothes, campfire → What to Bring cards). Rendered with `image-rendering: pixelated`.
- `flyers/young-adults.jpg`, `flyers/youth.jpg` — official flyers, shown in the Flyers section and linked from the track cards.
- `share.jpg` — link-preview (og:image) graphic, referenced as `share.jpg?v=2`. If you ever replace it, bump the `?v=` number in both meta tags or WhatsApp/Facebook will keep the cached old image.

## Hosting & deployment

- **Live site: https://southregionyouth.org** — served by **Cloudflare Pages**, connected to the GitHub repo `KaizokuZard-hash/camp-ezekiel`. Every push to `main` auto-deploys (takes ~30–60s).
- GitHub Pages also serves the same repo at https://kaizokuzard-hash.github.io/camp-ezekiel/ (legacy from initial setup; harmless).
- Domain is registered and DNS-managed at Cloudflare.
- To deploy any change: commit and `git push` to `main`. That's it.
- Local preview: any static server, e.g. `python3 -m http.server 4321` in this folder.

## Facts the owner has locked in (do NOT change without asking)

- Price is **$150 per person** (a later flyer said $155 — owner said keep $150).
- Venue is **Camp Victory, 2953 Willafa Woods Rd, Cartwright, OK 74731** (a later flyer
  showed an "Egan Camp & Retreat" sign — owner said keep Camp Victory). Venue site: https://www.campvictory.info/
- Price includes food & accommodation.
- Registration Google Form and Zelle payment (Southregionyouth@gmail.com, memo
  "Camp Ezekiel & [your name]") are the registration flow — both links are in `index.html`.
- Camp coordination phone: +1 (469) 882-6878.
- Church name is **Forward In Faith Ministries International** (early drafts misread the
  logo as "Rooted In Faith" — that's wrong).

## Design language

- Two-track color system from the flyers: navy/purple (#1e2a78, #3a2f8f) = Young Adults,
  gold/orange (#f5a623, #e8890b) = Youth. CSS variables at the top of `index.html`.
- Playful touches the owner asked for: animated hero gradient + floating hype text
  ("Camp oh yeah!", "South Region are you ready?", "Camp Ezekiel!"), glow orbs,
  pixel-art icons instead of emojis. Animations respect `prefers-reduced-motion`.
- Owner prefers the dark logo in a white circle for the hero (white-logo-on-gradient was
  offered and declined).

## Git/GitHub

- Repo: https://github.com/KaizokuZard-hash/camp-ezekiel (branch `main`).
- On a new machine: authenticate with `gh auth login` (or a PAT) before pushing.
- Commit author used so far: KaizokuZard-hash <blacklightning77887@gmail.com>.
