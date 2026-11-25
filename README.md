# Sizzle & Serve — Kali's Kitchen 🍳

An original, complete cooking game built for the make.fun bounty
**"Make the best cooking game"** — https://make.fun/bounty/best-cooking-game-20261125-0137
($250, 10 places; ends Wed Nov 25, 2026, 5:07 PM Tehran; Round 1 closes 8:07 AM Tehran).

## The game

You run a busy little kitchen. Customers order dishes from the order board;
you chop, grill and boil ingredients, build the dish on your plate, and serve
it before the customer's patience runs out. Earn **120 coins** before your
2:30 shift ends — but **3 walk-outs** ends the shift in failure.

- **Order board** (top): up to 3 live orders, each with a dish, price,
  required ingredients, and a patience bar. Ingredients already on your
  plate are ticked off on the order.
- **Kitchen stations**: 🔪 Chopping Board (veggies, 2s), 🔥 Grill (patty, 4s),
  🍲 Pot (pasta 5s, egg 3s). Click a station when its bar turns green to
  plate the item. Leave food too long (4s grace) and it **burns** — click
  the station to throw it away.
- **Ingredients on the counter** (8): 🍞 Bun, 🥩 Patty, 🧀 Cheese,
  🥬 Lettuce, 🍅 Tomato, 🍝 Pasta, 🍳 Egg, 🥫 Sauce. Bun, cheese and sauce
  go straight on the plate; the rest need prep first.
- **Plate & serving**: the plate shows your dish mid-assembly. When it
  matches an order exactly, the Serve button lights up green. Serve the
  wrong dish and you lose 3 coins. Faster service = bigger tip (up to +5).
- **Timer, score, levels**: 2:30 shift clock with a bar, coin target,
  dishes served, walk-out counter. Orders spawn faster and patience gets
  shorter as you serve more.
- **Win / lose / restart**: win screen with 1–3 stars, lose screen with a
  tip, restart button. Pause, mute, and restart controls in the header.
- **Sound**: tiny WebAudio beeps (no audio files). Mute with the button or `M`.
- **Controls**: mouse (click everything) and keyboard —
  `1`–`8` ingredients, `Space` serve, `T` trash plate, `P` pause,
  `M` mute, `R` restart, `Enter` start.

## Recipes

| Dish | Ingredients | Price |
|---|---|---|
| Classic Burger 🍔 | Bun + Patty + Cheese + Lettuce | $12 |
| Veggie Burger 🍔 | Bun + Lettuce + Tomato + Cheese | $12 |
| Garden Salad 🥗 | Lettuce + Tomato + Cheese + Sauce | $10 |
| Pasta Alfredo 🍝 | Pasta + Cheese + Sauce | $14 |
| Cheesy Pasta 🍝 | Pasta + Cheese + Tomato | $13 |
| Breakfast Plate 🍳 | Egg + Tomato + Bun | $11 |

## How to run

No install, no network, no server needed — the game is a single file:

1. Open `game/index.html` in a desktop browser (Chrome recommended).
2. Click **▶ Start Cooking!** and play.

Everything (art, sound, logic) is inline in `index.html`. There are no
external requests, no CDN, no images to load — it plays fully offline from
its own files. Art is emoji + CSS; sounds are generated with WebAudio.

## Files

- `game/index.html` — the complete game (HTML + CSS + JS, ~28 KB)
- `main.ts` — the kit's entry program (copies `game/` + `screenshots/`,
  writes `dossier.json` with `vendor/makefun-game.ts`)
- `vendor/makefun-game.ts` — the kit's dossier library, copied unchanged
  (sha256 `dc67187521b24025ff952f8c231485a6eb92d6d71d29edd2a08154ffb4376129`)
- `screenshots/` — 4 real renders (see below)
- `LICENSE` — MIT (from the starter kit)
- `README.md` — this file

## Verification done

- `node --check` on the extracted script: **passes** (no syntax errors).
- Headless logic test (Node `vm` with a stubbed DOM, `/tmp/test-game.js`
  — not part of the deliverable): **18/18 checks passed**, covering
  game start, first order spawn, instant vs. prepped ingredients,
  grill/chop timing, burn + discard, serving a correct burger
  (score increases), wrong-dish −3 penalty, walk-out strike, and
  timeout loss below target.
- Confirmed zero external URLs / network references in `index.html`.
- **Screenshots taken 2026-11-25 ~06:43 Tehran in a real browser**
  (playwright + sandboxed Chromium), all 1280×800 PNG, each under the
  256 KiB cap: `shot1-start.png` 185 KB (start screen),
  `shot2-gameplay.png` 191 KB (fresh orders), `shot3-cooking.png`
  191 KB (stations cooking), `shot4-progress.png` 193 KB (burnt
  lettuce/patty, pasta ready). First by name (`shot1-start.png`) is
  the cover. Visually verified.
- **Repo layout assembled and dossier builds:** `mkdir -p /tmp/cooking-out
  && MAKEFUN_OUTPUT_DIR=/tmp/cooking-out node main.ts` (Node v24.22.1)
  exits 0 and writes `game/`, `screenshots/` (4 files) and
  `dossier.json` (schema `makefun/dossier/v1`). The vendor file was
  checked before running: only `node:crypto` / `node:fs` / `node:path`
  imports, no network, no child processes.

## What is still missing to submit (do NOT do without the user)

The repo layout is now complete. Still needed, all in the user's own
browser / GitHub account:

1. **Create a public GitHub repo** under @kalidefi (created after the
   competition opened) and push this folder's contents to its root.
2. **Upload the AI coding-agent transcripts** of the sessions that
   built this game with the submission.
3. **Link GitHub (@kalidefi) and X (@kali_defi2) on make.fun** (not yet
   linked as of Nov 24), then submit via the make.fun entry flow and
   complete the **wallet signature**.
4. **Deadline — Round 1 closes Wed Nov 25, 8:07 AM Tehran**; final
   deadline 5:07 PM Tehran the same day.

Nothing here was submitted, signed, posted, funded, or linked, and no
passwords, seed phrases, or API keys were requested or used.
