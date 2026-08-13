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
  A card in two colours is a two-cleaner job.
- **Timeline** — property × day, bookings and cleanings in one grid. This is the view that
  survives 50+ units.
- **Changes** — what moved in the imported platform calendars since the last review: cancelled
  stays, shifted check-outs, overlapping bookings. The system never edits the schedule itself;
  it hands the decision to a manager.
- **Properties / Cleaners** — the registries, with rates, standard duration, crew size, payouts.
- **Reports** — per cleaner (where, how many hours, what they earned) and per property
  (how many cleanings, who did them, what it cost).
- **Assigning a job** — pick up to two cleaners, split the pay, see a live preview of the
  WhatsApp message before it goes out. Conflicts are caught in the form: the cleaner is already
  booked, the manager is across town, the cleaning won't finish before the 15:00 check-in.

Interface switches between **Russian, English and Hebrew** (Hebrew flips the whole layout to RTL).

## Demo data

August 2026 · 8 Eilat properties (villas and apartments) · 5 cleaners · 40 cleanings.
This week is staffed; from Sunday 16 August everything is still open — that backlog is the point.

## What it is not

A mockup. There is no back end: no real calendar sync with Airbnb or Booking, and no real
WhatsApp delivery. Changes you make live in the page and disappear on reload.

---

## О чём это

Интерактивный макет сервиса для графика уборок в краткосрочной аренде (Эйлат).
Один самодостаточный `index.html` — открывается в браузере, ничего собирать не нужно.

Цель сервиса — просто и понятно составлять расписание уборок, доводить задание до исполнителя
через WhatsApp и вести учёт: кто, где, сколько часов, сколько денег. Отчёты собираются по людям
и по объектам.

Интерфейс переключается между русским, английским и ивритом. Настоящей синхронизации с
площадками и настоящей отправки в WhatsApp в макете нет.
