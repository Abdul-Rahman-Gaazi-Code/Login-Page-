# Diagonal Login Card

 A fully responsive login UI featuring a hand-built diagonal-split background, smooth hover states, and zero JavaScript frameworks — just HTML and CSS doing the heavy lifting.

---

## Features

- Diagonal-split card background built from rotated, layered shapes — no images, pure CSS
- Truly fluid responsive layout — scales smoothly from small phones to desktop, no awkward jumps
- Custom button with hover, active, and focus states, plus an animated arrow icon
- Username and password fields with icon labels
- Social login section for Instagram, Facebook, and Twitter
- Keyboard-accessible focus styling

---

## Tech Stack

- **HTML5** — semantic structure
- **CSS3** — Flexbox, `clamp()`, `aspect-ratio`, `transform`, `overflow: hidden`

No frameworks, no build tools — just the fundamentals, used deliberately.

---

## How the Responsiveness Works

Instead of writing a pile of `@media` breakpoints, this project leans on a few modern CSS techniques to scale fluidly at any screen size:

css
.background {
  width: clamp(280px, 90vw, 500px);
  aspect-ratio: 2 / 3;
}
## Lessons I Learned

Building this taught me more about *why* things break than just how to fix them. Here's what stuck with me:

**1. `position: absolute` listens to its closest positioned parent — not the whole page.**
My login form kept positioning itself against the entire screen instead of the card. Turns out it wasn't sitting inside a `position: relative` parent, so it had nothing nearby to "anchor" to. The fix wasn't more CSS — it was just moving the element to the right spot in my HTML. I learned that HTML structure and CSS work together more than I thought.

**2. Fixed pixel sizes don't scale. Percentages and `clamp()` do.**
I had shapes sized in exact pixels, made for one screen size. The second the screen changed, everything looked wrong. Switching to percentages and `clamp()` let everything resize on its own — no more guessing new sizes for every device.

**3. `aspect-ratio` is easier than managing width and height separately.**
Setting a fixed width and a fixed height means both can fight each other when the screen resizes. With `aspect-ratio`, I only set the width, and the height follows automatically, keeping the same shape no matter the size.

