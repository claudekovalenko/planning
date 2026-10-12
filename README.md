# Planning

A planning app that doesn't keep its own priorities. It reads them from the
**Vision**, **Building & Blessing** and **Centered** apps, and every task and goal
has to say which of them it serves.

## How it ties together

All the apps are served from `claudekovalenko.github.io`, so they share one
`localStorage`. Planning reads:

| Source | Key | What becomes a priority |
|---|---|---|
| Vision | `vision-app-v2` | the vision text, central and ancillary pursuits, growth edges, daily rhythms |
| Building & Blessing | `building-and-blessing/v5` | Deep items (in your priority order), Current, Blessing, Enjoyment |
| Centered | `centered.v1` | the major decisions (church, marriage) |

Nothing is written back to those apps. Edit a priority where it lives and
Planning picks it up the next time you switch to it. If an app hasn't been opened
in this browser yet, Planning uses a built-in snapshot and says so at the bottom
of the page.

Priorities fall into groups, walked in this order:

- **Carry:** the center (remain in Jesus), central pursuits, deep responsibilities
  and major decisions. These are numbered, and the week is measured against them.
- **Never ahead of those:** growth edges, supporting (ancillary and current) work,
  and blessing and joy.
- **Serves nothing in particular:** always available, so you can be honest about it.
  It shows up in red in the review.

## Views

- **Today:** the vision at the top, the daily rhythms to check off with the last
  seven days, today's list (star the one to three that matter most), unfinished
  items from earlier, and a prompt when something you carry has nothing planned
  this week.
- **Week:** go down each priority in order and give it one concrete step, or
  mark it as resting this week on purpose. A meter shows what share of the week
  goes to what you carry.
- **Season:** goals for a 12-week season (the length is editable), each tied to a
  priority. Tasks can be linked to a goal.
- **Review:** what got done, broken down by what it served. It flags priorities
  where nothing got finished, blessing work done while things you carry stayed
  open, and work tied to nothing. It also has three reflection prompts and moves
  everything still open to next week.

## Running it

Open `index.html`, or serve the folder (`python3 -m http.server`). There is no
build step and nothing to install. Over HTTPS it can be installed as a PWA and
works offline. GitHub Pages deploys it from this branch via
`.github/workflows/pages.yml`, at <https://claudekovalenko.github.io/planning/>.

Data stays in your browser under `planning.v1`. Use "Save a backup" and "Load a
backup" at the bottom of the page to move it between devices.
