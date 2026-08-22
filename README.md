# Workout Checklist

A single-file, offline-friendly workout checklist for the phone. Tap an exercise to tick it off; progress is saved in `localStorage` so it survives a reload, and **Reset checklist** clears it for the next session.

## Use it

Open `index.html` in a browser, or visit the GitHub Pages URL. On iOS, use Share → *Add to Home Screen* for a full-screen, app-like version.

## Editing the workout

Everything lives in `index.html`. The exercises are a single array near the top of the `<script>` block:

```js
var exercises = [
  { id: 'goblet-squat', name: 'Goblet squat', meta: '2 sets x 8-12' },
  ...
];
```

Add, remove, or reorder entries there. Keep `id` values unique and stable — they are the keys used for saved progress, so changing an `id` resets that exercise's state.

No build step, no dependencies.
