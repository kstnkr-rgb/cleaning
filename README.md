# Cleaning ops console — demo

Interactive mockup of a cleaning-scheduling service for short-term rentals in Eilat.

**[Open the demo →](https://kstnkr-rgb.github.io/cleaning/)** (enable GitHub Pages on the `main` branch to serve it)

Everything lives in a single self-contained `index.html` — no build step, no dependencies.
Open the file in a browser and it runs.

## What it does

An owner rents out a few dozen apartments and villas. Every guest check-out is a cleaning that
has to be handed to somebody, confirmed, and paid for at the end of the month. The demo shows
how that would be run from one screen.

- **Schedule** — a month grid of cleanings, one card per check-out, colour-coded by cleaner.
  A card striped in several colours is a job shared by a team.
- **Timeline** — property × day, bookings and cleanings in one grid. This is the view that
  survives 50+ units.
- **Booking changes** — what moved in the imported platform calendars since the last review:
  cancelled stays, shifted check-outs, overlapping bookings. The system never edits the schedule
  itself; it hands the decision to a manager.
- **Change history** — an append-only log of everything that touched the schedule, written as a
  diff: `time 11:30 → 13:00 · team Yael B. ₪200 → Yael B. ₪260`. Sync events are credited to the
  system, manual ones to the manager who made them.
- **Properties / Cleaners** — the registries, with rates, standard duration, team size, payouts.
- **Reports** — per cleaner (where, how many hours, what they earned) and per property
  (how many cleanings, who did them, what it cost).
- **Assigning a job** — build a team of up to three, type what each person gets, and see a live
  preview of the WhatsApp message each will receive. A cleaner cannot be put on a job without a
  figure next to her name. Conflicts are caught in the form: she is already booked, the manager is
  across town, the cleaning won't finish before the 15:00 check-in.

A cleaning costs exactly the sum of what the team was paid — there is no second, separately
edited price to drift out of step with the card on the calendar.

Every change is written to browser storage the moment it happens, so a reload after a crash picks
the schedule back up. The header shows when the last save landed; **Reset the demo** puts the
starting data back.

Interface switches between **Russian, English and Hebrew** (Hebrew flips the whole layout to RTL).

## Demo data

August 2026 · 8 Eilat properties (villas and apartments) · 5 cleaners · 40 cleanings.
This week is staffed; from Sunday 16 August everything is still open — that backlog is the point.

## What it is not

A mockup. There is no back end: no real calendar sync with Airbnb or Booking, and no real
WhatsApp delivery. Edits are kept in your own browser and go no further.

---

## О чём это

Интерактивный макет сервиса для графика уборок в краткосрочной аренде (Эйлат).
Один самодостаточный `index.html` — открывается в браузере, ничего собирать не нужно.

Цель сервиса — просто и понятно составлять расписание уборок, доводить задание до исполнителя
через WhatsApp и вести учёт: кто, где, сколько часов, сколько денег. Отчёты собираются по людям
и по объектам.

Интерфейс переключается между русским, английским и ивритом. Настоящей синхронизации с
площадками и настоящей отправки в WhatsApp в макете нет.
