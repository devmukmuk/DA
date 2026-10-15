# DA known problems

Everything already known to be wrong or missing in DA, with a way around it where there is one. If you find
something that isn't here, please [report it](https://github.com/devmukmuk/DA/issues) (see
[Reporting a problem](https://da.gamenightbymike.com/verification.html#reporting-a-problem) in the test plan).

**Kind:** a *defect* is something DA does wrong; a *limitation* is something it doesn't do yet.
**Severity:** *high* - it can change many files or stop you working; *medium* - it gets in the way, and
there's a way around it; *low* - a nuisance.

| # | Problem | Kind | Severity | Issue |
|---|---|---|---|---|
| 1 | [A mistyped folder in `da tag` tags every file](#1-a-mistyped-folder-in-da-tag-tags-every-file) | defect | high | [#2](https://github.com/devmukmuk/DA/issues/2) |
| 2 | [Windows blocks DA.exe on some PCs](#2-windows-blocks-daexe-on-some-pcs) | limitation | medium | [#3](https://github.com/devmukmuk/DA/issues/3) |
| 3 | [Two DA windows changing one archive at once](#3-two-da-windows-changing-one-archive-at-once) | defect | medium | [#4](https://github.com/devmukmuk/DA/issues/4) |
| 4 | [An older archive's Open DA.cmd can't find DA installed with Python](#4-an-older-archives-open-dacmd-cant-find-da-installed-with-python) | defect | medium | [#5](https://github.com/devmukmuk/DA/issues/5) |
| 5 | [`da update` can fail while another DA window is open](#5-da-update-can-fail-while-another-da-window-is-open) | defect | low | [#6](https://github.com/devmukmuk/DA/issues/6) |
| 6 | [Menu 4 only undoes duplicates](#6-menu-4-only-undoes-duplicates) | limitation | low | [#7](https://github.com/devmukmuk/DA/issues/7) |
| 7 | [A video's time can be a few hours off](#7-a-videos-time-can-be-a-few-hours-off) | defect | low | [#8](https://github.com/devmukmuk/DA/issues/8) |
| 8 | [Contact sheets are slow for months with many iPhone photos](#8-contact-sheets-are-slow-for-months-with-many-iphone-photos) | limitation | low | [#9](https://github.com/devmukmuk/DA/issues/9) |
| 9 | [Older photos show as "Unknown camera"](#9-older-photos-show-as-unknown-camera) | limitation | low | [#10](https://github.com/devmukmuk/DA/issues/10) |
| 10 | [Videos show as a VIDEO card on contact sheets](#10-videos-show-as-a-video-card-on-contact-sheets) | limitation | low | [#11](https://github.com/devmukmuk/DA/issues/11) |
| 11 | [Videos aren't used for places or location folders](#11-videos-arent-used-for-places-or-location-folders) | limitation | low | [#12](https://github.com/devmukmuk/DA/issues/12) |
| 12 | [Some old videos have no date DA can read](#12-some-old-videos-have-no-date-da-can-read) | limitation | low | [#13](https://github.com/devmukmuk/DA/issues/13) |
| 13 | [A few terminal commands print raw JSON](#13-a-few-terminal-commands-print-raw-json) | limitation | low | [#14](https://github.com/devmukmuk/DA/issues/14) |

## 1. A mistyped folder in `da tag` tags every file

**Issue:** [#2](https://github.com/devmukmuk/DA/issues/2)

**What happens:** `da tag` takes files or folders, then the tags to add. A folder name that doesn't exist (a
typo, or `photos\organized\2020-11` instead of `photos\organized\2020\2020-11`) is taken as a *tag*; with no
real folder named, DA then adds that "tag" to **every file in `photos\organized`**, without asking.

**What it changes:** only an extra tag in each sidecar (no photo is moved, renamed or changed).

**Way around it:** check the folder exists before tagging. To undo, take the tag off again (with the same words,
joined by `-`): `da tag --remove photos-organized-2020-11`.

**Fix planned:** a word that looks like a path but doesn't exist stops with "No such folder"; tagging the whole
archive asks first. Test plan step U2.

## 2. Windows blocks DA.exe on some PCs

**Issue:** [#3](https://github.com/devmukmuk/DA/issues/3)

**What happens:** on a PC with Windows' **Smart App Control** turned on, `DA.exe` may not run: *"an
application control policy has blocked this file"*, or Windows Security warnings. DA.exe isn't digitally signed,
and Smart App Control decides each PC on its own (the same file can run on one PC and not another).

**Way around it:** install DA with Python instead (free, about ten minutes): see
[Install DA with Python](https://da.gamenightbymike.com/#install-da-with-python-if-windows-blocks-daexe). It
works the same, and updates with `da update`. Please don't turn Smart App Control off for DA.

## 3. Two DA windows changing one archive at once

**Issue:** [#4](https://github.com/devmukmuk/DA/issues/4)

**What happens:** two commands that change the same archive at the same time (say `da run` in one window and
`da location lookup` in another) can fail with *"database is locked"*, or leave confusing records. Commands
that only look (Status, Report, What needs review) are fine alongside.

**Way around it:** one changing command per archive at a time. Different archives at once are fine.

**Fix planned:** a lock, so a second DA says "another DA is working in this archive" instead.

## 4. An older archive's Open DA.cmd can't find DA installed with Python

**Issue:** [#5](https://github.com/devmukmuk/DA/issues/5)

**What happens:** an archive made before version 2026.10.21 has an `Open DA.cmd` that only looks for
`DA.exe`. After installing DA with Python (which sets DA.exe aside), double-clicking it says *"DA is not
installed on this PC"*. The install updates the launchers of the archives this PC knows (`da archives`), so
this only happens for an archive the PC hadn't opened before.

**Way around it:** in a terminal, `da setup "<that archive's folder>"`. It rewrites `Open DA.cmd` (nothing
else changes in the archive).

## 5. `da update` can fail while another DA window is open

**Issue:** [#6](https://github.com/devmukmuk/DA/issues/6)

**What happens:** with DA installed with Python, `da update` replaces DA's files; if another DA window is using
them, Windows may not let it, and it says the update didn't finish.

**Way around it:** close every DA window (including the menu), open one new terminal, run `da update` again.

## 6. Menu 4 only undoes duplicates

**Issue:** [#7](https://github.com/devmukmuk/DA/issues/7)

**What happens:** **4 Undo last set-aside** puts back the last set of duplicates. Splits, merges, location
folders and paired Live Photo videos can be undone too, but only from a terminal.

**Way around it:** each of those prints an **Undo** line when it finishes (`da intake undo "<file>"`); copy and
run it. The files are also in the archive's `output\runs\` folders (`…-split\split-moved.csv`,
`…-merge\merge-copied.csv`, `…-location-group\location-moved.csv`).

## 7. A video's time can be a few hours off

**Issue:** [#8](https://github.com/devmukmuk/DA/issues/8)

**What happens:** some cameras and older phones store a video's time in UTC (world time). DA converts it with
**this PC's** time zone, so a video recorded while travelling (or on a PC set to another zone) can be named a
few hours early or late, and very rarely land on the day before or after. Videos whose names carry the local
time (`VID 00000-20091016-2017.3gp`) and iPhone videos are right.

**Way around it:** shift them: `da date shift "<video or folder>" --by -3h` (or `+2h`, …), then
`da validate "<its folder>" --mode repair`.

## 8. Contact sheets are slow for months with many iPhone photos

**Issue:** [#9](https://github.com/devmukmuk/DA/issues/9)

**What happens:** making a contact sheet decodes every photo to draw its small picture; iPhone HEIC photos are
slow to decode (about 10 seconds for 170 photos). This mostly shows during big runs and `da contact-sheets`.

**Way around it:** none needed: it only happens when a month's photos change. **Planned:** keep the small
pictures, so a sheet made again decodes nothing.

## 9. Older photos show as "Unknown camera"

**Issue:** [#10](https://github.com/devmukmuk/DA/issues/10)

**What happens:** photos filed by an older version of DA (before 2026.10.14) don't have their camera details
yet, so contact sheets put them all under **Unknown camera**, and they have no `camera:`/`owner:` tags.

**Way around it:** run `da tag` once in that archive (it reads each photo's camera details; slow the first
time), then `da contact-sheets photos\organized`.

## 10. Videos show as a VIDEO card on contact sheets

**Issue:** [#11](https://github.com/devmukmuk/DA/issues/11)

**What happens:** contact sheets show each video as a dark **VIDEO** card with its length, not a picture from
the video. **Planned** for a later version.

## 11. Videos aren't used for places or location folders

**Issue:** [#12](https://github.com/devmukmuk/DA/issues/12)

**What happens:** `da location lookup` and location folders (menu **L**) use photos only; a video recorded at
the same place stays in the month folder. **Planned** for a later version.

**Way around it:** move a video into a location folder yourself (with its `.meta.json`); DA accepts it there.

## 12. Some old videos have no date DA can read

**Issue:** [#13](https://github.com/devmukmuk/DA/issues/13)

**What happens:** many old `.mpg`, `.wmv` and some `.avi` files don't record when they were made, so DA can't
date them; they wait in intake under **3 What needs review** ("No date").

**Way around it:** give them a date: menu **D** (a folder at a time), or
`da date set "<video>" --date 2006-06`.

## 13. A few terminal commands print raw JSON

**Issue:** [#14](https://github.com/devmukmuk/DA/issues/14)

**What happens:** some older terminal commands (`da findit tags`, `da db inspect`) print their results as JSON
text, which is hard to read.

**Way around it:** look for `"match_count"` and the file paths; the menu and the newer commands print plain
sentences.
