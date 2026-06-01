# 🦁 Lion's ABC Typing

A tiny, distraction-free typing game for toddlers (2+) — built in an afternoon with
Claude Code and a very particular two-year-old.

The whole thing is **one self-contained `index.html`**, open it to get playing.

👉 **[Play it live here](https://sabhiram.github.io/toddler-abcs/)** 
📄 single HTML file
🔊 uses your device's built-in voice

---

## The idea

Show one big CAPITAL letter and a matching picture. The child finds that key on the
keyboard. Get it right and the app celebrates and says **"A for Apple!"** — then moves
on. Get it wrong and a friendly animal gently nudges you toward the right key. That's
the whole loop.

## How it plays

1. Tap **▶ Let's Play!**
2. **Pick a color and a buddy animal** — chosen once for the whole game. Your color
   tints the letters, keyboard, and confetti; your animal becomes the on-screen cheerleader.
3. A big letter appears with a matching emoji picture. Press that key → confetti, a
   happy chime, and your buddy says **"A for Apple!"**
4. The **⭐ score** climbs with every correct key. A row of dots tracks progress to the
   next **mini-celebration**, which fires **every 10 correct keys** with a big confetti
   blast and a fanfare.

Miss a key and you get an escalating, never-scary hint: a spoken *"That's B — let's
find A!"*, then the on-screen keyboard lights up the right key, then a bouncing 👆
points right at it.

## Run it

It's a single file — nothing to install.

- **Locally:** double-click `index.html`, or open it in any modern browser.
- The first **▶ Let's Play!** tap is what unlocks sound and voice (browsers require a
  user gesture before they'll make noise).

## Grown-up settings (the ⚙️ gear, top-right)

A panel small enough that little fingers won't stumble into it:

- **Voice** on/off and **sound effects** on/off
- **Say the letter each round** — the buddy names each new letter
- **Which voice** and **speaking speed** (pick whatever sounds friendliest on your device)
- **Keyboard helper:** *when she misses* (default) · *always on* · *never*

Settings are remembered in the browser.

## Built to survive a toddler

The hard part of a 2-year-old's app isn't teaching — it's the key-mashing. So the game:

- ignores held-key auto-repeat and any non-letter keys;
- **locks input during celebrations** so a flurry of taps can't skip ahead;
- debounces repeated wrong keys and cancels queued speech, so mashing never floods the
  voice with a backlog of corrections;
- never repeats the same letter twice in a row.

There's also a ⛶ fullscreen button — but exiting is left to the grown-up; the page
stays an ordinary, well-behaved browser tab.

## Make it your own

Everything lives in `index.html`, near the top of the `<script>`:

- **`ITEMS`** — the emoji + word for each letter (a few options per letter, picked at
  random). Swap in your kid's favorites.
- **`PALETTE`** and **`ANIMALS`** — the colors and buddies on the chooser screen.
- **`ROUND_LEN`** — how many correct keys earn a mini-celebration (default `10`).
