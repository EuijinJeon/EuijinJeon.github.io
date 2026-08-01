# 전의진 ❤︎ 지예은 — 모바일 청첩장

<https://euijinjeon.github.io/>

GitHub Pages (`main` branch, root) serves this directly. No build step — push and it's live.

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole invitation: markup, styles, and behavior. This is the only file to edit for content or design changes. |
| `photos/hero.webp` | Main visual under the header |
| `photos/g1…g9.webp` | Gallery photos, in display order |
| `bgm.mp3` | Background music (Schumann, *Waldszenen* Op. 82 — Richter, 1956) |
| `og.png` | 1200×630 link preview image for KakaoTalk / social shares |

## Where things live in `index.html`

Each section is marked with a `<!-- ====== NAME ====== -->` comment:

`HEADER` · `MAIN VISUAL` · `INVITATION TEXT` · `PARENTS` · `GALLERY` ·
`DATE & TIME` · `LOCATION` · `ACCOUNT` · `FOOTER` · `BGM` · `TOAST`

Behavior lives in the single `<script>` at the bottom: toast, account accordion,
copy-to-clipboard, `.ics` calendar download, and background music.

### Notes

- **Calendar** is static markup for October 2026 (Oct 1 = Thursday). Sundays and
  holidays (3·5·9) are rose, Saturdays slate, the wedding day is a filled circle.
  Changing the date means regenerating those cells.
- **Add-to-calendar** builds an `.ics` file with an `Asia/Seoul` VTIMEZONE block, so
  it opens in whatever calendar app the guest's phone uses — no Google lock-in.
- **Music** can't autoplay until the visitor interacts, so it starts on the first
  tap/scroll and pauses when the tab is hidden.
- **OG tags** use absolute `https://euijinjeon.github.io/` URLs — they must stay
  absolute or link previews break.

## Local preview

```bash
python3 -m http.server 4173
```

Then open <http://localhost:4173>.

## Source

Designed in Claude Design (project *Wedding Invitation Calendar Button*). This repo
holds the plain static version, which is what's deployed.
