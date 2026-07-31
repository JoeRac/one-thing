# ONE THING

A single-file focus reminder for a spare monitor.

Put the one thing that actually matters on a screen you don't otherwise use.
Every N minutes the whole display flashes — a gold wash, a specular sweep, the
words inverting to black — so a glance pulls you back to it.

No build, no server, no dependencies. One HTML file.

## Use it

**Hosted:** <https://joerac.github.io/one-thing/>

**Local:** double-click `index.html`. That's the whole install, and it works
offline.

Either way:

1. Click the text and type your one thing. It saves as you type.
2. **Size** slider — scale the type to fill the screen.
3. **Flash every** slider — 1 minute up to 12 hours.
4. **Full screen**, then park it on the second display.

The control bar and the cursor fade out after ~3.5s of no input, so what's left
on screen is just the words.

### Keys

| Key | |
|---|---|
| `F` | full screen |
| `T` | flash now (preview it) |
| `S` | toggle the chime |
| `Esc` | stop editing |

### Also in there

- Four accent colours — gold, ice, ember, verdant.
- An optional chime on flash, off by default.
- A hairline progress rail along the bottom edge counting down to the next flash.
- The countdown survives a reload, so refreshing doesn't restart the cycle.

## Autosave, and why the hosted copy is still private

Everything — text, size, interval, colour, sound — goes to `localStorage` under
`onething.v1`, debounced 400ms.

There is no server, no database, no network call anywhere in this file. The
hosted page is a static asset; what you type stays in the browser that typed it.
Publishing the page publishes the *app*, never your text — someone opening the
URL gets an empty screen and their own private copy.

The flip side: storage is per-origin and per-browser, so the hosted copy and the
local file keep separate text, and clearing site data clears it. Pick one and
stick with it.

Autosave works from `file://` in Chrome, which is what macOS opens `.html` with
by default. Some browsers block storage on `file://`; if yours does, the app says
so in the top-left corner instead of silently losing your text. Use the hosted
URL, or serve the folder locally:

```bash
python3 -m http.server -d . 8000
```

## License

MIT
