# Weekend Reset

A single-page cleaning checklist built for ADHD. It shows one "Next up" task at a time, with a Done button, a Skip for now button and an optional 10-minute timer. Tasks are grouped by room in the order you would walk through the apartment, each with a rough time estimate and a progress bar.

No build step, no dependencies. The whole app is `index.html`.

## Run it

Open `index.html` in any browser.

## Put it on GitHub Pages

```bash
git init
git add index.html README.md
git commit -m "Add Weekend Reset checklist"
git branch -M main
git remote add origin https://github.com/<your-username>/weekend-reset.git
git push -u origin main
```

Then in the repo go to **Settings → Pages**, set the source to **Deploy from a branch**, pick `main` and `/ (root)`, and save. The site appears at `https://<your-username>.github.io/weekend-reset/` after a minute or two.

## Saving progress

Checked tasks are saved in the browser's `localStorage`, so they persist between visits on the same device and browser. They do not sync across devices, and clearing site data resets them. The **Start over** button clears every check.

## Change the tasks

Open `index.html` and edit the `GROUPS` and `TASKS` arrays at the top of the `<script>` block.

- `GROUPS` sets the sections, in display order. Each has an `id`, a `name` and a short `note`.
- `TASKS` sets the checklist. Each task has an `id` (unique), a group `g`, an estimate in minutes `m`, the text `t`, and an optional `tip` shown on the Next up card.
- A task in the group with id `sunday` is treated as a later task. It is listed but never offered as "Next up" and does not count toward today's progress.

## Change the colors

All colors are tokens at the top of the `<style>` block. The light theme is in the first `:root` rule, and the dark theme is repeated in the two rules below it. Dark mode follows the device setting.
