# MIDI Drum Pad

A 3×3 pad of percussion sounds that runs in the browser. Click a pad, or Tab to it and press Space or Enter, and it plays a short drum sample. It is built with HTML, CSS and a small amount of JavaScript, and it has no libraries.

**Live demo:** [alura-midi-sigma-sable.vercel.app](https://alura-midi-sigma-sable.vercel.app)

## How it works

- Each pad is a `<button class="tecla tecla_pom">` (the second class names the instrument), and each sound is an `<audio>` element with a matching id.
- `main.js` loops over the pads once, builds the id of the matching audio element from the pad's class name, and sets the click handler. `tocaSom()` checks that the element exists and really is an `<audio>` before calling `play()`.
- Pressing Space or Enter on a focused pad adds an `ativa` class, which gives the visual "pressed" state. It is removed on key release.
- The pads sit in a CSS Grid with three equal columns (`repeat(3, 1fr)`).

The pad labels (Pom, Clap, Tim, Puff, Splash, Toim, Psh, Tic, Tom) are in Portuguese.

## Run it

No build step and no dependencies. Clone the repo and open `index.html` in a browser.

```bash
git clone https://github.com/victorhubarb/alura-midi.git
cd alura-midi
```

## Project structure

```
index.html   Pads and audio elements
main.js      Click and keyboard handling
css/         reset.css, estilos.css
sounds/      Nine .wav samples
```

## Known gaps

- Hitting the same pad again while its sound is still playing does nothing, because `play()` does not restart a sample that is already running. Setting `currentTime = 0` first would fix it.
- The sound files are named after the keys Q, W, E, A, S, D, Z, X and C, but those keys are not mapped yet. Only the mouse and the focused Space or Enter keys work.
- There are no media queries, so the layout is made for larger screens.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
