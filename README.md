# ONE THING

A single-file focus reminder for a spare monitor.

Put the one thing that actually matters on a screen you don't otherwise use.
Every N minutes the whole display flashes — a gold wash, a specular sweep, the
words inverting to black — so a glance pulls you back to it.

No build, no server, no dependencies. One HTML file, opened straight off disk.

![the flash](docs/flash.png)

## Use it

Double-click `index.html`. That's the whole install.

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

## Autosave

Everything — text, size, interval, colour, sound — goes to `localStorage` under
`onething.v1`, debounced 400ms.

This works from `file://` in Chrome, which is what macOS opens `.html` with by
default. Some browsers block storage on `file://`; if yours does, the app says so
in the top-left corner instead of silently losing your text. Serving the folder
over `http://` fixes it anywhere:

```bash
python3 -m http.server -d . 8000
```

## License

MIT
