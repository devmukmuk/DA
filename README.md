# DA - Digital Archive

**Latest version:** 2026.10.33 (2026-10-16)

DA files your photos, videos and scanned documents by the date they were taken. It sets exact
duplicates aside, names each file by its date, and puts it in a `YYYY\YYYY-MM` folder, with a contact
sheet for every month. It never deletes anything, and it asks before it moves anything.

## Get it (Windows)

- **Download** [DA.exe](https://github.com/devmukmuk/DA/releases/latest/download/DA.exe), then follow
  [Getting started](https://da.gamenightbymike.com/#getting-started) in the user guide.
- **Windows won't run DA.exe?** ("an application control policy has blocked this file") Install DA
  [with Python instead](https://da.gamenightbymike.com/#install-da-with-python-if-windows-blocks-daexe): free, and about ten minutes, once.
- **Already have DA?** Type `da update` (DA installed with Python), or download DA.exe again and run
  `.\DA.exe install`.
- **Long paths:** `da install` offers to turn on Windows' long paths, so files in deep folders (paths of
  260 characters or more) can be moved. See [Long paths](https://da.gamenightbymike.com/#long-paths).

## Read

- **The user guide:** https://da.gamenightbymike.com (also as a [PDF](https://da.gamenightbymike.com/DA-User-Guide.pdf))
- **What changed in each version:** [CHANGELOG.md](CHANGELOG.md)
- **Testing DA?** The [test plan](https://da.gamenightbymike.com/verification.html) (also as a
  [PDF](https://da.gamenightbymike.com/DA-Test-Plan.pdf) to print) and the [known problems](https://da.gamenightbymike.com/defects.html)

## What's new in v2026.10.33

### New
- da rename --apply with undo, --save keeps old patterns, menu N Naming

## Found a problem?

[Open an issue](https://github.com/devmukmuk/DA/issues): what you did, what you expected, what happened instead, and your version
(type `da version`). Leave out anything private (names, photos, folder paths you'd rather not share).

This repository holds the latest release, the user guide's pages and the changelog. It is updated
automatically each time a new version of DA is published.
