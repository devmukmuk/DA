# DA changelog

What changed in each version of DA, newest first. The user guide is at https://da.gamenightbymike.com.

## v2026.10.87 - 2026-10-27

### New
- Word, Excel and PowerPoint documents show their first page

### Fixed
- Catch libtiff's "Bad code word" lines from damaged fax scans

### Faster
- Step 3b compares only pairs with a picture being filed, and remembers them

## v2026.10.86 - 2026-10-26

### New
- da convert makes a JPG beside each RAW that has none

### Fixed
- Dates: a camera-set file prefix (8W9A1900) is a frame number, not a year

## v2026.10.85 - 2026-10-26

### New
- Show RAW and edit pairs on sheets, shares, history; edits follow their RAW into location folders
- File each edit beside its RAW; the layout is the archive's choice
- Keep a photographer's exports and pair each with its RAW

## v2026.10.84 - 2026-10-26

### New
- Set a Mac's hidden "._" files aside in step 3

### Fixed
- Drop index rows outside the archive; step 3 names a missing kept copy

## v2026.10.83 - 2026-10-25

### New
- Archives.json keeps each archive's details

## v2026.10.82 - 2026-10-24

### New
- Contact sheets: click a picture on a sheet to open the file

## v2026.10.81 - 2026-10-24

### New
- Contact sheets: no Hash256 line under each document

## v2026.10.80 - 2026-10-24

### New
- Contact sheets: document sheets show a secret as a red border; File/Folder/Hash256/Dates in one size

## v2026.10.79 - 2026-10-24

### New
- Contact sheets: --kind document makes one sheet per year of documents

## v2026.10.78 - 2026-10-24

### New
- da ocr notes each document's dates and Secrets yes/no in its sidecar

## v2026.10.77 - 2026-10-24

### New
- Places: da location group takes a year and does each of its months

## v2026.10.76 - 2026-10-24

### New
- Places: --skip-title and --set-title give every group one answer

## v2026.10.75 - 2026-10-24

### Fixed
- Places: groups named by location.untitled keep a folder per place

## v2026.10.74 - 2026-10-24

### New
- Places: location.untitled names a group you don't title ({city}, {camera}-{owner} ...)

## v2026.10.73 - 2026-10-23

### New
- da holding checks every held copy for its original; --empty sends those to the Recycle Bin

## v2026.10.72 - 2026-10-22

### Fixed
- Tags: a raw file filed on its own is a photo for da tag

## v2026.10.71 - 2026-10-22

### Fixed
- Checking: a camera's frame number (IMG_1900) is not a year

## v2026.10.70 - 2026-10-22

### Guide
- Single quotes for folder patterns in da-archive.yaml; how the two folder settings fit

## v2026.10.69 - 2026-10-22

### New
- Keep every folder a file came in from; {from:N} tokens and folder: tags

## v2026.10.68 - 2026-10-22

### New
- Find files by the folder they came from, their camera or part of a name
- Link an edit named after its photo; guide: edit a filed photo

## v2026.10.67 - 2026-10-21

### New
- One year or a decade for --years; set up the folder you're in

## v2026.10.66 - 2026-10-21

### Fixed
- da facial scan ran out of memory on a big archive

## v2026.10.65 - 2026-10-21

### New
- Confirmed names on contact sheets, shares and history; Process intake step 12 Faces

## v2026.10.64 - 2026-10-20

### New
- Process intake's steps after filing - 8 camera owners, 9 tags, 10 places, 11 location folders

## v2026.10.63 - 2026-10-20

### New
- The dashboard's People page - confirm suggestions, name groups

## v2026.10.62 - 2026-10-20

### New
- Canon CR2 / CR3 (and other raw files) on their own are filed as photos
- da facial scan, people, suggest, rename, forget

## v2026.10.61 - 2026-10-19

### New
- Bursts and blurry photos marked (never moved)

## v2026.10.60 - 2026-10-19

### New
- Re-saved copies set aside, edited and cropped versions linked; contact sheets and shares show them

## v2026.10.59 - 2026-10-19

### New
- Resized copies set aside (the same picture, smaller); shares list the copies in holding

### Fixed
- Make services/similar a regular package (the wheel's package finder needs __init__.py)

## v2026.10.58 - 2026-10-19

### New
- Yellow face boxes and names on contact sheets and shares; people and tags in share emails

### Fixed
- An empty GPS block isn't a position

## v2026.10.57 - 2026-10-19

### New
- da picasa - Picasa's faces, names, captions and stars into the sidecars
- Dates: old Word files' creation dates and dates written out in names
- Voice notes follow their photo; warn when a camera clock was reset

## v2026.10.56 - 2026-10-19

### New
- A file's whole story, --hash, --everywhere, --duplicates

## v2026.10.55 - 2026-10-19

### New
- da history - the archive's latest changes, from DA's own records

## v2026.10.54 - 2026-10-19

### New
- Film strips on the first page, each photo's details in the email, the archive named

## v2026.10.53 - 2026-10-18

### Fixed
- Each person gets their own email - Gmail refused "To: undisclosed-recipients" (Invalid To header)

## v2026.10.52 - 2026-10-18

### New
- da update finds, downloads, checks and swaps in the newest DA.exe; fix the dashboard losing its files

## v2026.10.51 - 2026-10-18

### Fixed
- Send with a plain HTTPS call - no "UnknownApiNameOrVersion: gmail v1"; Python installs get the google extra

## v2026.10.50 - 2026-10-18

### New
- Logging: every change to an archive is logged, with the computer's name

## v2026.10.49 - 2026-10-18

### New
- da share - email a simple contact sheet from your Gmail; the dashboard's Share button

## v2026.10.48 - 2026-10-18

### New
- Pictures - thumbnails by month, enlarge, set as desktop, open its folder

## v2026.10.47 - 2026-10-18

- Small fixes and tidying.

## v2026.10.46 - 2026-10-18

### New
- da archives move - move an archive to another drive; index, undo logs and list follow

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
