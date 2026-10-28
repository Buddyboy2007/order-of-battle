# Order of Battle

Every ranked military on Earth, on one map, fighting each other without you.

**Play it: https://buddyboy2007.github.io/order-of-battle/**

All 198 sovereign states are on the board and none of them are yours. Each one is
run by the same engine, picking its moment, its neighbour and its service. You pick
a flag to follow and watch what happens to it.

A turn is a month. Wars are not settled in one — they run for years, and the line
moves a province at a time until somebody runs out of country.

## How a war runs

- **Neighbours only.** A state may declare on a country it shares a border with. A
  state with no foreign land border — an island, or one that has swallowed everyone
  around it — puts troops on ships instead, and only then.
- **Doctrine.** Each side fights the way its own numbers say it fights. The United
  States comes out air-led with everything behind it; Chile comes out naval-led;
  Switzerland is ground and nothing else. None of it is hand-written — it is read
  off the pillar scores and the hardware each country keeps per soldier.
- **The line.** Every month the front shifts a little toward whoever is winning the
  exchange, and both sides lose materiel doing it. A province changes hands only
  when the line finally breaks *and* the garrison standing on it is gone.
- **Conquest pays.** Take a country and you inherit every soldier it could field and
  roughly half its materiel and industry. That is what lets a winner keep winning.
- **Occupied ground does not stay quiet.** Resistance decays where it is garrisoned
  and festers where it is not, and a dead state can rise again on its old borders.
- **DEFCON.** The board tracks how close the whole thing is to the end: Fade Out,
  Double Take, Round House, Fast Pace, Cocked Pistol. Cocked Pistol is rare and it
  means somebody's arsenal is about to be overrun.

## What settles an exchange

Each month on each front, the engine works in log-odds:

| term | what it is |
|---|---|
| technology | spend per soldier, soft-saturated — the heaviest term in the sum |
| mass | formations actually in reach, saturating until the odds pass 6:1 |
| doctrine | how well each side's way of fighting suits this theatre |
| defensibility | remoteness and border exposure, derived from the map, never assigned |
| home ground | interior lines and reserves within reach |
| nuclear | hesitation, long before anything is used |
| luck | a triangular draw, every month |

Two rules the weights are fitted to, measured over ~53,000 sampled exchanges:
the better-equipped side wins about two thirds of the fights where equipment and
numbers disagree, and once the numbers pass six to one they win anyway, 83% of
the time.

## Data

Pillar scores, rankings and inventories: [globalmilitary.net](https://www.globalmilitary.net/compare/countries/)
ATLAS Index, 160 ranked states, 22 October 2026. Manpower 10%, Ground 20%,
Naval 20%, Air 25%, Nuclear 10%, Defence budget 15%. States outside the ranking
are on the map and estimated.

Coastlines are Natural Earth 1:110m, projected Equal Earth.

## Running it

One file, no build, no dependencies.

```bash
python3 -m http.server 8777
```

Then open http://localhost:8777/.
