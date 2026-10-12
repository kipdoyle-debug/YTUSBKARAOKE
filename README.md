# Karaoke Mic (web app)

One file, no install: `index.html`. Paste a YouTube karaoke link, press **Mic on**, sing through your USB mic.

## Run it
Browsers only allow microphone access and YouTube embeds from a real web address, so don't double-click the file. Use one of these:

**Local (easiest)** — in this folder:
```
python -m http.server 8000
```
then open http://localhost:8000 in Chrome or Edge.
(No Python? `npx serve` works too.)

**Put it online (free, works from any PC)** — drop `index.html` on Netlify Drop (app.netlify.com/drop), GitHub Pages, or Cloudflare Pages. You get an https link to bookmark.

## Controls
- **Floating buttons on the video:** the big mic button turns the mic on/off (clicking the video steals keyboard focus, so the M key may not work there). The small button makes the video area fullscreen; the mic keeps running.
- **Test sound:** plays a short chime to the output chosen in "Your voice plays to". If you can't hear it, that output isn't the one your speakers or headphones are on.
- **Song volume:** balances the song against your voice. Works for videos playing inside the page, not the pop-up fallback.
- **Feedback guard:** mutes the mic if a squeal lasts more than about a second. Untick it if it trips while you sing loudly.
- **Second mic:** click "+ Add a second mic", pick it, and set its volume. Keep both volumes low with speakers.
- **Auto-reconnect:** if you plug in a device or change the Windows default output while the mic is on, the app reconnects by itself.

## Tips
- Wear headphones, or the mic will pick up the song and feed back.
- Use Chrome or Edge on Windows. "Your voice plays to" is hidden in browsers that can't choose an output (Firefox, Safari); set your headphones as the Windows default output there.
- The video plays through the Windows default output. Make that the same headphones as "Your voice plays to".
- Echo cancellation, noise suppression and auto gain are off on purpose, for lower delay and a natural voice. A limiter caps sudden loud spikes.
- Wired USB mic and wired headphones give the least delay. Bluetooth adds a lot.
- Some channels (Karaoke Fun, for example) turn off embedding. YouTube enforces that, so those videos can't play inside the page. When that happens the app shows a panel with "Open in a pop-up window". Place the pop-up next to the app and sing as usual: the mic keeps working because both windows play through the same Windows output.
- Ads still play unless you skip them or have YouTube Premium.
