# 🦁 Toddler Games

A tiny, distraction-free set of typing **adventures** for toddlers (2+) — built with
Claude Code and a very particular two-year-old. It started as just the ABCs and is
growing into a little collection of lessons.

The whole thing is **one self-contained `index.html`**, open it to get playing.

👉 **[Play it live here](https://sabhiram.github.io/toddler-abcs/)** 
📄 single HTML file
🔊 uses your device's built-in voice

---

## The adventures

- **01 · Letters** — one big CAPITAL letter and a matching picture; find that key.
  Right → *"A for Apple!"* and confetti. Wrong → a friendly nudge toward the key.
- **02 · Words** — a picture and a short word spelled out (🐱 **CAT**). The current
  letter glows; type the letters in order. Each correct letter is spoken (*"C… A… T…"*),
  and finishing the word says *"C, A, T spells cat!"*.
- **03 · Counting** — a neat grid of N (1–9) emojis and a box showing the number
  (🐱🐱🐱🐱 → **[ 4 ] CATS**). Press that number key. Teaches recognizing the count
  *and* finding the digit on the keyboard.
- **04 · Counting (pro)** — same, but the number box is empty (**[ ? ] CATS**). Count
  the emojis yourself and type the right digit.
- *More coming soon* — the picker shows what's next.

## How it plays

1. Tap **▶ Let's Play!**
2. **Pick a color and a buddy animal** — chosen once and kept across every adventure.
   Your color tints the letters, keyboard, confetti, **and the whole screen's mood**;
   your animal becomes the on-screen cheerleader.
3. **Pick an adventure** from the lesson picker.
4. Play! The **⭐ score** climbs with every success. A row of dots tracks progress to the
   next **mini-celebration** — every **10 letters** (Letters) or **5 words** (Words) — a
   big confetti blast, a fanfare, and a bouncing banner.
5. Tap the **🏠 Home** button (top-left) any time to switch adventures. Color and buddy
   are remembered.

Miss a key and you get a gentle, never-scary hint: a spoken *"That's B — let's find A!"*.
After two hints the app simply lights up the right key with a pointing 👇 and leaves it
there; the key you pressed glows and slowly fades so you can see where it was.

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
- **`WORDS`** — the Words adventure's list. It's **derived automatically** from `ITEMS`:
  any short single word (3–4 letters) becomes a spellable word with its emoji, so adding
  a short word to `ITEMS` adds it here too. (~41 words today, covering 23 starting letters.)
- **`COUNT_ITEMS`** — the Counting adventures' emojis, also **derived from `ITEMS`** and
  auto-pluralized (`pluralize` + a small `PLURAL_EXC` map; `COUNT_SKIP` drops uncountable
  or plural-only nouns like *water*/*grapes*). ~85 items today.
- **`PALETTE`** and **`ANIMALS`** — the colors and buddies on the chooser screen.
- **`LESSONS`** — the list of adventures. Each has an `id` the round logic switches on,
  a display `num`/`icon`/`title`/`blurb`, a `roundLen` (successes per mini-celebration),
  a `cheer` line, and an optional `locked: true` to show a "coming soon" teaser card.
  Add an entry plus a branch in `showRound`/`onRight` to grow the game.
