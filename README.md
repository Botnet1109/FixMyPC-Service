# FixMyPC Service

My personal tech support and vlog website — on-demand remote IT and desktop support.

Live at: https://botnet1109.github.io/FixMyPC-Service/

## What it covers
- Windows, Linux, macOS help
- Printer software issues
- Software installation & troubleshooting
- Basic hardware part replacements
- System build

## Built with
HTML, CSS & vanilla JavaScript — no frameworks, no build step. GitHub Pages serves the repo root directly.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole site — markup, styles and script in one file |
| `404.html` | Custom "page not found" page, picked up automatically by GitHub Pages |
| `og-image.png` | 1200×630 preview image used when the link is shared on WhatsApp / X / LinkedIn |
| `robots.txt` | Allows search engines and points at the sitemap |
| `sitemap.xml` | Single-page sitemap |

## Adding a YouTube video (the only thing you normally need to touch)

Open `index.html`, scroll to the `<script>` block at the bottom, and find `var VIDEOS`.

Add a new entry like this:

```js
{
  url:   "https://www.youtube.com/watch",
  tag:   "Windows",
  title: "Your video title",
  desc:  "One short line about what it covers."
},
```

Save and push. That's it — the card, the real thumbnail and the click-through link are all generated automatically. Any of these link formats work:

- `https://www.youtube.com/watch
- `https://youtu.be/VIDEO_ID`
- `https://www.youtube.com/shorts/VIDEO_ID`
- `https://www.youtube.com/live/VIDEO_ID`

You can add as many entries as you want; the grid wraps on its own. Delete a `{ ... }` block to remove a card.

**A card with `url: ""` shows a dashed "Coming soon" card instead of a link.** The three cards currently in the list are placeholders for videos that don't exist yet — paste the real link into one and it instantly becomes a clickable card with its own thumbnail.

The other settings sit just above the video list:

```js
var CHANNEL_URL        = "https://youtube.com/@panwar0911";
var CHANNEL_VIDEOS_URL = CHANNEL_URL + "/videos";
var EMAIL              = "Varunsingh09@proton.me";
```

Change the channel URL or email there once and every link on the page updates — nav, hero button, vlog section, about card and footer.

## Contact form

The form has no backend. On submit it validates the fields and opens the visitor's email app with the name, email, issue type, device and description pre-filled, addressed to the address in `EMAIL`. A "copy the details instead" button is there for visitors whose browser has no mail app configured, so a message is never lost.

If you later want submissions delivered without relying on the visitor's mail client, swap in a form endpoint (Formspree, Getform, or a Cloudflare Worker) — the validation and message-building logic can stay as is.

## Contact
varunsingh09@proton.me
