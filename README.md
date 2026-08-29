# Workout Checklist

A single-file, offline-friendly workout checklist for the phone. Two workouts — **Day A (Legs & core)** and **Day B (Upper, hips & core)** — with a toggle to switch between them. Tap an exercise to tick it off; progress is saved in `localStorage` so it survives a reload, and **Reset** clears the day you're currently looking at.

Each day keeps its own progress, and the day you last viewed is remembered.

## Use it

Open `index.html` in a browser, or visit the GitHub Pages URL. On iOS, use Share → *Add to Home Screen* for a full-screen, app-like version.

## Editing the workouts

Everything lives in `index.html`. Both days are defined in a single `days` array near the top of the `<script>` block:

```js
var days = [
  {
    key: 'a',
    label: 'Day A',
    focus: 'Legs & core',
    items: [
      { id: 'a-goblet-squat', name: 'Goblet squat', kit: 'Kettlebell', sets: '2–3 sets', reps: '8–12' },
      ...
    ]
  },
  ...
];
```

- `sets` and `reps` are rendered as `sets × reps`, so write them as they should read (`'2 sets each side'`, `'20–40 sec'`).
- `kit` is the equipment, shown in clay after the dose. Leave it as `''` for bodyweight-only moves and nothing is shown.
- `id` values must be **unique across both days** — they are the keys used for saved progress. The day prefix (`a-` / `b-`) is what keeps exercises that appear in both days, such as Front plank, from sharing a tick. Changing an `id` resets that exercise's state.

Adding or removing exercises is enough on its own — the numbering, the tally bar, and the counts all follow the array length.

No build step, no dependencies.
