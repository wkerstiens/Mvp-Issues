# Mvp: issues and feedback

Public issue tracker for **Mvp**, a World of Warcraft (Retail, Midnight) addon
that recaps a Mythic+ key when it ends and picks an MVP using a role-aware score
(damage, healing, interrupts, dispels, avoidable damage and deaths).

This repository holds no source code. It exists so bug reports and suggestions
have one place to live.

## Install

Get the addon from [CurseForge](https://www.curseforge.com/projects/1742129), or
unzip it into `World of Warcraft/_retail_/Interface/AddOns/` so the folder is
`AddOns/Mvp`. Then reload the game.

## Using it

- A recap prints when a key completes. `/mvp report` prints it again on demand.
- `/mvp show` opens the rankings window: an MVP card, a class-coloured score bar
  per player, awards, and saved runs. Hover a row to see how its score was built.
- `/mvp history [n]` lists your last 10 keys, or prints run *n*.
- `/mvp explain` prints the score math for every player. It is always local.
- `/mvp settings` shows the toggles; `auto`, `autoparty`, `awards` and
  `autoreset` each flip with `/mvp <name>` (or add `on` / `off`).
- `/mvp debug` prints what the damage meter is returning, and who else in the
  group runs Mvp. It is always local.

Things worth knowing:

- The automatic recap goes to party chat only when everyone in the group is in
  your guild or on your friends list; otherwise it prints locally. If several
  people in a group run Mvp, only one of them posts it.
- While a key or combat is running the game can hide player data from addons.
  Mvp waits and retries, and shows a one-line message instead of a recap full of
  "Unknown". Run `/mvp report` again once the key or combat has ended.
- Scores are judged within a role (damage against other damage dealers, healing
  against other healers). A lone healer or tank has nobody to be compared with in
  some categories, so those are left out rather than handed out as free points.

## Posting an issue

1. [Search the existing issues](../../issues) first; yours may already be there.
2. [Open a new issue](../../issues/new/choose) and pick the matching form:
   *Bug report*, *Scoring looks wrong*, or *Suggestion*.
3. Include, as far as you can:
   - what you expected and what happened instead
   - the addon version (shown in the AddOns list on the character-select screen)
   - the dungeon and key level, if it happened in a key
   - for a scoring complaint, the output of `/mvp explain` right after the run
   - for missing or "n/a" data, the output of `/mvp debug`
   - any Lua error text (an addon such as BugSack makes these easy to copy)
   - a screenshot, if it is a display problem

`/mvp explain` and `/mvp debug` list character names. Remove any you would
rather not share.
