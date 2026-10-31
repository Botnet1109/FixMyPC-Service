# FixMyPC Service

My personal tech support and vlog website — on-demand remote IT and desktop support.

## What it covers
- Windows, Linux, macOS help
- Printer software issues
- Software installation & troubleshooting
- Basic hardware part replacements
- System build

## Built with
HTML, CSS & vanilla JavaScript — single file, no frameworks, no build step.

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

You can add as many entries as you want; the grid wraps on its own. Delete a `{ ... }` block to remove a card. A video with `url: ""` shows a card that links to the channel instead.

The other settings sit just above the video list:

```js
var CHANNEL_URL        = "https://youtube.com/@panwar0911";
var CHANNEL_VIDEOS_URL = CHANNEL_URL + "/videos";
var EMAIL              = "Varunsingh09@proton.me";
```

Change the channel URL or email there once and every link on the page updates — nav, hero button, vlog section, about card and footer.

## Contact form

The form has no backend. On submit it validates the fields and opens the visitor's email app with the name, email, issue type, device and description pre-filled, addressed to the address in `EMAIL`. If you later want submissions delivered without relying on the visitor's mail client, swap in a form endpoint (Formspree, Getform, or a Cloudflare Worker) — the validation logic can stay as is.

## Contact
varunsingh09@proton.me
