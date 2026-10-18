# DA changelog

What changed in each version of DA, newest first. The user guide is at https://da.gamenightbymike.com.

## v2026.10.45 - 2026-10-18

### New
- da archives delete - only when every file exists elsewhere, to the Recycle Bin

## v2026.10.44 - 2026-10-18

### New
- da split --organized - split filed files into the archives for their years

## v2026.10.43 - 2026-10-18

- Small fixes and tidying.

## v2026.10.42 - 2026-10-18

### Faster
- Contact sheets: keep each thumbnail in .da\thumbs by its hash, so remade sheets don't open photos
- A big run ~2.5x faster - settings read once, filing reuses the preview, quick verify, HEIC previews

## v2026.10.41 - 2026-10-17

### Fixed
- Restore text nodes between searches

## v2026.10.40 - 2026-10-17

### New
- Contact sheets: show held duplicate copies

## v2026.10.39 - 2026-10-17

### Fixed
- Enable navigation while typing search

## v2026.10.38 - 2026-10-17

### New
- Add searchable guide with match navigation

## v2026.10.37 - 2026-10-16

### Fixed
- Adapt checklist columns to viewport
- Reset timers and surface controls

## v2026.10.36 - 2026-10-16

### New
- Add automatic step timing

## v2026.10.35 - 2026-10-16

### New
- Location folders in any layout (da location group 2019-04); OCR and merge follow the folder patterns

## v2026.10.34 - 2026-10-16

### New
- Folder patterns - file into any layout; da rename --folder moves filed files

## v2026.10.33 - 2026-10-16

### New
- da rename --apply with undo, --save keeps old patterns, menu N Naming

## v2026.10.32 - 2026-10-16

### Fixed
- Checking: an older sidecar's duplicate_status "original" no longer stops a run

## v2026.10.31 - 2026-10-16

### New
- Camera, owner, place and more name tokens; da rename previews the names

### Fixed
- Add tokens.py (the token* ignore rule hid it); ignore token*.json/.pickle only

## v2026.10.30 - 2026-10-16

### Fixed
- Intake: long paths - one failed move no longer stops a run; da install offers Windows' long paths

## v2026.10.29 - 2026-10-15

### New
- da tag ocr - read the text in pictures, tag text/document, move documents
- Run in the background by default; da dashboard --stop, --foreground

## v2026.10.28 - 2026-10-15

### New
- Pass / skip / fail per step with the step's reported problems; dashboard years one by one, most first

### Guide
- O9 uses the default intake\photos folder
- Test plan steps for da dashboard (O6-O13)

## v2026.10.27 - 2026-10-15

### New
- da dashboard - the archive in the browser, kept up to date
- The online test plan tracks a tester's name, version, dates and ticks, reports problems per step, counts open reports, saves a dated PDF and starts again on a new version

## v2026.10.26 - 2026-10-15

### Guide
- Link the known problems to their public issues (devmukmuk/DA #2-#14)
- A 221-step test plan and the known problems, published on the site and in the public repo

## v2026.10.25 - 2026-10-15

### New
- Contact sheets: summary page, a section per camera/owner, GPS and sidecar-version marks, 3x4 or 4x5 layout

## v2026.10.24 - 2026-10-15

### New
- Sidecars: schema 2 - blocks only, old fields lifted (kept under legacy when they disagree); da sidecar upgrade with backup and restore; video sidecars say video

## v2026.10.23 - 2026-10-14

### New
- Videos: file videos like photos by the date recorded inside them

## v2026.10.22 - 2026-10-14

### New
- Dates you know better - da date list/set/shift/clear and menu D; a date set by hand wins; roadmap doc

## v2026.10.21 - 2026-10-14

### New
- Installing: DA run by Python for PCs where Smart App Control blocks DA.exe; da update; guide explains installing Python

## v2026.10.20 - 2026-10-14

### New
- da merge --from <other archive> copies in what the other copy has and this one does not
- da report - a dated one-page PDF about the archive (what is filed, by year, cameras, places) in output
- Menu opens with Status (and after Process intake), 7 lists this PC's archives, S Split; every command logged to logs\da.jsonl

### Fixed
- Documents: pypdf's warnings about small PDF flaws no longer flood the terminal (da split, da run)

### Faster
- Report: count camera, owner and place tags in one pass

## v2026.10.19 - 2026-10-14

### New
- da split moves intake files from other years into the archive for those years, undoable

### Fixed
- Split: 'Moved 1 file'

## v2026.10.18 - 2026-10-14

### New
- Places: da location rename and set (--place, --same-as, --clear); regrouping adds new photos to an existing location folder
- Places: da location group and menu L - group a month's GPS photos into titled location folders, undoable
- Places: validate and da run accept location folders (YYYY-MM <title>) as a photo's home
- Places: da location lookup - towns and states for GPS photos, spot cache, place tags

## v2026.10.17 - 2026-10-14

### Guide
- Config tokens and Location/GPS workflows sections; {tag}/{tags} use your tags

## v2026.10.16 - 2026-10-14

### New
- Tags: DA saves camera owners in da-archive.yaml itself - asks in da tag --cameras, or --owner

## v2026.10.15 - 2026-10-14

### Fixed
- Tags: a relative folder updates the index; one sidecar read and write per photo

## v2026.10.14 - 2026-10-14

### New
- da tag - camera details kept in every new sidecar, automatic tags from them, and your own tags

## v2026.10.13 - 2026-10-14

### New
- Live Photo videos travel with their photo; da pair-movies; da heic-to-jpg
- Contact sheets - a PDF of every photo in a folder, made by da run and kept current by da validate

## v2026.10.12 - 2026-10-14

### New
- DA User Guide at da.gamenightbymike.com, published from the public devmukmuk/DA repo

### Fixed
- Checking: repair stops on intake and outside folders (use da run); --help works outside an archive

## v2026.10.11 - 2026-10-13

### New
- --archive works after the command; a folder's own archive is used; outside folders are copied into intake
- Menu: browse intake subfolders - open, filter by name, go up, process any level

## v2026.10.10 - 2026-10-13

### New
- Intake\photos, docs and scans by default; the intake folder decides photo vs document

## v2026.10.9 - 2026-10-13

### New
- Checking: date documents by the date inside them; read MM-DD-YYYY and month-year names

## v2026.10.8 - 2026-10-13

### Fixed
- Archive commands stop outside an archive; db commands handle a never-built index

## v2026.10.7 - 2026-10-13

### New
- The interactive menu - `da` on its own (and Open DA.cmd) opens it

### Fixed
- `da` works in the same window right after installing

## v2026.10.6 - 2026-10-13

### Fixed
- The archive launcher ran itself in a loop - now "Open DA.cmd" calling DA.exe by full path
- `da check` on a repair report; the `da` console script's entry point

## v2026.10.5 - 2026-10-13

### New
- An archive is a folder with da-archive.yaml - no profiles; setup adopts, DA.cmd, da archives

## v2026.10.4 - 2026-10-13

### New
- `da setup` + `da run` - the whole workflow, repeatable on any PC
- Intake: `da intake` status / hash / set-aside / undo through the database
- Index: `da db build` indexes the whole archive; `da validate` at top level
- Checking: flag a photo whose name date differs from EXIF date taken
- Checking: raw files follow the photo with the same name
- Duplicates: inventory photos outside organized and set aside redundant copies

### Fixed
- Convert every file timestamp safely (sidecar save, indexers, ScanIt)
- Checking: an unreadable file modified time is an uncertain date, not a crash
- Checking: an EXIF date of 1970-01-01 / 1980-01-01 00:00 is no date
- Index: a rebuild keeps hashes computed earlier while the file is unchanged
- Sidecars: keep file.sha256 in step with validate's hash
- Intake: also hash unhashed organized files a copy could match
- Index: leave modified_at blank for a timestamp Windows can't convert
- Checking: a moved raw file's sidecar records where it came from
- Photos: read DateTimeOriginal from the Exif sub-IFD
- Checking: a date-only file name takes the time from same-day EXIF
- Checking: collision names keep the extension; identical targets are duplicates
- Checking: take capture dates from file names; review instead of filing guesses
- Checking: one set of photo/document extensions; classify scanned images
