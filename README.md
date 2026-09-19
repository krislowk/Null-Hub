<div align="center">

<img src="logo.gif" width="120" alt="Null Hub logo" />

# Null Hub

**A Steal An Egg script hub.**

[![Status](https://img.shields.io/badge/status-live-4ade80?style=flat-square&labelColor=0a0a0a)](#)
[![Keyless](https://img.shields.io/badge/keyless-yes-edededed?style=flat-square&labelColor=0a0a0a)](#)
[![Place](https://img.shields.io/badge/steal_an_egg-only-767676?style=flat-square&labelColor=0a0a0a)](#)

</div>

---

## Loadstring

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/krislowk/Null-Hub/refs/heads/main/NullHub.txt"))()
```

Paste it into your executor, hit run, done. Only works in **Steal An Egg**.

---

## What's in it

| Tab | What it does |
|---|---|
| **Home** | Trending scripts pulled live from ScriptBlox. Refresh anytime. |
| **Hop** | One tap joins the lowest-pop server. Re-runs Null Hub on the new server so you don't have to re-execute. |
| **Search** | Search ScriptBlox by name. Filter to keyless-only, or search whatever game you're in. |
| **Keyless** | 26 keyless Steal An Egg hubs. Tap, wait, done. No Discord, no key. |
| **Key** | 12 hubs that need a key. Links to their sites. |
| **Favs** | Star anything. Saved to file so they survive restarts and hops. |
| **Visuals** | Player ESP with names and distance. Fullbright, fog removal, FOV slider. |
| **Optimize** | Frame boost, kill particles, kill lighting FX, mute sounds. All reversible. |

---

## How it works

The hub is a single Lua file. Nothing fancy. It builds a UI with `Instance.new`, talks to the Roblox API and ScriptBlox to fetch server lists and scripts, and executes them through `loadstring`.

**Auto-exec:** When you hop, the hub queues itself to re-run on the new server using `queue_on_teleport`. Set `HUB_URL` at the top of the script to your raw URL and it reloads automatically.

**Files it writes:**
- `NullHub_Favs.txt` — starred scripts
- `NullHub_ServerHop.txt` — recently visited servers (1 hour cooldown)
- `NullHub_Config.txt` — auto-exec settings

---

## Dev setup

If you're forking this and want to change things:

**The script** — one file, `NullHub.txt`. Everything is in there. Sections are marked with `-- ═══ SECTION ═══` headers so you can jump around.

**The website** — `index.html` at the repo root. Plus `logo.gif` and `preview.png`. Any static host works: GitHub Pages, Cloudflare Pages, Netlify, Vercel.

**Adding scripts to the hub:** find the `KEYLESS_SCRIPTS` or `HAVEKEY_SCRIPTS` table near the top and add an entry:

```lua
{ name = "SCRIPT NAME", url = "https://raw.githubusercontent.com/..." },
```

**Changing the logo:** swap the asset ID in `LOGO_ID` at the top of the script.

**Changing the theme:** all colors live in the `T` table right below the logo. It's a flat palette — background, surface, card, border, text, dim, white, plus green/red/gold for states.

---

## Requirements

- A modern Roblox executor (Delta, Arceus X, Xeno, Krnl, Synapse, Fluxus, Wave)
- A Steal An Egg session — the hub exits early if you're anywhere else
- Mobile or PC, both work

---

## Credits

Built by [krislowk](https://github.com/krislowk).

Scripts linked in the hub belong to their respective authors. Null Hub just loads them.

Not affiliated with Roblox or Steal An Egg.

---

## License

Do whatever you want with it.
