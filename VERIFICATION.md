# DA test plan

Thank you for testing DA. This plan walks through everything DA does, step by step: first with the
**menu** (what most people use), then with **commands typed in a terminal** (for things the menu doesn't
have). Each step says what to do and what you should see. Mark it **passed** when it works, **skipped** when
you can't try it, and **failed** when it doesn't: write down the step's number (like **D7**) and what happened,
and see [Reporting a problem](#reporting-a-problem).

**On the website** this page keeps track for you: fill in your name at the top (and the version, which is
filled in already), then mark each step with its buttons: **✓ passed** (green), **○ skipped** (yellow) or
**✗ failed** (red); press it again to clear it. The page counts your progress and remembers it - in this
browser, on this computer only. Each step's **Report** button opens a new problem report with the step, your
name and the version already filled in, and marks the step failed. Problems already reported for a step (by
you or anyone) are listed under it, with whether they're still open and their labels. **Save as PDF** keeps a
dated copy of your results; when a new version of DA comes out, **Start again on a new version** clears them for
the next round. On paper, use the [printable checklist](https://da.gamenightbymike.com/DA-Test-Plan.pdf).

The website has one **Start timing** button. When you're ready, start it; the first unfinished step is timed.
Choose that step's passed, skipped or failed result to save its time and automatically move timing to the next
unfinished step. Use **Pause timing** for breaks; resume when you're ready. Each section's time is the sum of
its steps, and the overall time is the sum of all section times. Timing is saved in this browser along with
your results; starting again on a new version clears it.

You don't need to do it all in one sitting: each part starts from where the one before left off. The whole
plan takes a few evenings. The [user guide](https://da.gamenightbymike.com) explains anything this plan
mentions; the [known problems](https://da.gamenightbymike.com/defects.html) list what's already known, so you
don't need to report those.

## Before you start

- **Use copies, never your only photos.** DA never deletes anything and asks before it moves anything, but
  this is a test: copy some photos into a new folder and test with those.
- **A Windows PC** with about 5 GB free, and an internet connection for a few steps (places, updates).
- **Write down your DA version** (it's shown in step A5) when you report anything.
- Words used here: an **archive** is the folder DA looks after; **intake** is where you put new files; a
  **sidecar** is the small `.meta.json` file DA keeps beside each photo; the **menu** is what opens when you
  double-click an archive's `Open DA.cmd` (or type `da`).

### Make a test kit

Make a folder `C:\DA-test-kit` and put copies of these in it. The more kinds you have, the more of the plan
you can try; skip a step whose files you don't have and mark it **skipped**.

| Folder in the kit | What to put in it | Used in |
|---|---|---|
| `phone` | 20-50 photos from a phone (JPG or HEIC), some taken outdoors (they have a location) | C, H, K, L |
| `phone` | 2-3 iPhone **Live Photos** (each is a `.HEIC` or `.JPG` plus a `.MOV` with the same name) | I |
| `phone` | 2-3 ordinary videos (`.mov` or `.mp4`, longer than 5 seconds) | I |
| `camera` | 5-10 photos from a different camera (another phone, or a digital camera) | H, K |
| `scans` | 5 scans of old prints (JPG/PNG/TIFF that have **no date** in them or in their name) | G, J |
| `docs` | 3-5 PDFs (bills, letters) and a Word or Excel file | G |
| `doubles` | 3 photos that are **exact copies** of photos in `phone` (copy them again) | F |
| `old` | 3-5 photos taken in a different decade from the rest (say 2005 if the rest are 2020s) | M |
| `other` | an old camera video (`.AVI` / `.MPG`), a `.CR2`/`.NEF` raw file with its JPG, a screenshot | D, I |

## A. Install DA

| # | Do this | You should see | Result |
|---|---|---|---|
| A1 | Open https://da.gamenightbymike.com | The DA User Guide, with a **Download DA** button and a contents list on the left | ☐ |
| A2 | Click **Download DA** | `DA.exe` downloads (about 75 MB); if the browser asks, choose **Keep** | ☐ |
| A3 | In File Explorer, go to Downloads, click the address bar, type `powershell`, press Enter | A blue/black terminal window opens in Downloads | ☐ |
| A4 | Type `.\DA.exe install` and press Enter | "Installed C:\Scripts\DA\DA.exe and added it to your PATH" (or "already on your PATH") | ☐ |
| A4a | If instead you see *"an application control policy has blocked this file"* or a Windows Security warning that won't go away | Go to step **A10** (install with Python) and skip A5-A9 | ☐ |
| A4b | If you see *"Windows protected your PC"* | Click **More info**, then **Run anyway**; then A4 works | ☐ |
| A4c | At the end of A4, read the *Long paths* line | *Long paths: on*, or *Long paths are off* and *Turn long paths on now?*: answer **y**, click **Yes** in Windows' permission window; it says *Long paths: on* | ☐ |
| A4d | In File Explorer, right-click `C:\Scripts\DA\DA.exe`, **Properties**, **Details** | *File version* and *Product version* show the same version as `da version` (not 0.0.0.0) | ☐ |
| A5 | Close the terminal, open a **new** one (Windows key, type `powershell`, Enter), type `da version` | `DA v2026.10.…` - write this version down | ☐ |
| A6 | Type `da --help` | A list of commands (setup, run, status, archives, guide, …) | ☐ |
| A7 | Type `da guide` | The user guide opens in your browser | ☐ |
| A8 | Type `da guide --pdf` | The guide's PDF opens | ☐ |
| A9 | Type `da update` | It says which version you have and how to get the newest DA.exe | ☐ |
| A10 | *(Python install - only if Windows blocks DA.exe, or to test it)* Follow the guide's [Install DA with Python](https://da.gamenightbymike.com/#install-da-with-python-if-windows-blocks-daexe): install Python from python.org | `py --version` in a new terminal shows `Python 3.…` | ☐ |
| A11 | Type the guide's first line: `py -m venv C:\Scripts\DA\python` | No error; the folder `C:\Scripts\DA\python` exists | ☐ |
| A12 | Type the second line (`…python.exe -m pip install -r https://da.gamenightbymike.com/python/requirements.txt`) | It downloads and ends with "Successfully installed … devmukmuk-da-…" | ☐ |
| A13 | Type the third line (`…python.exe -m mindit install`) | "Installed C:\Scripts\DA\da.cmd (DA run by Python …)"; if a DA.exe was there: "Set aside DA.exe (now DA.exe.off)" | ☐ |
| A14 | New terminal: `da version` | The version, with **no** Windows Security pop-up | ☐ |
| A15 | `da update` | "Downloading the newest DA …" then "Now: DA v…" | ☐ |
| A16 | Outside any archive, type `da status` | "Not inside an archive" and how to open one (no crash) | ☐ |
| A17 | Type `da` on its own (outside any archive) | "You're not inside an archive" and an offer to create one (answer **n** for now) | ☐ |

## B. Create an archive

| # | Do this | You should see | Result |
|---|---|---|---|
| B1 | In a terminal: `da setup C:\DA-test\jane-archive-202x --years 2020-2029` | "Archive ready" and the folder's path | ☐ |
| B2 | Open `C:\DA-test\jane-archive-202x` in File Explorer | `da-archive.yaml`, `Open DA.cmd`, and folders `intake` (with `photos`, `docs`, `scans`), `photos`, `documents`, `output`, `logs` | ☐ |
| B3 | Open `da-archive.yaml` in Notepad (right-click, Open with, Notepad), then close it | `name: "jane-archive-202x"`, `years: "2020-2029"`, the intake folders, `contact_sheets: layout: 3x4` | ☐ |
| B4 | Double-click `Open DA.cmd` | A window opens: a box with the archive's name, folder and years, then the **Status** (intake: 0 files), then the menu keys | ☐ |
| B5 | Look at the menu | Keys **1-7**, **L**, **S**, **M**, **R**, **D**, **J**, **U**, **H**, **Q** | ☐ |
| B6 | Press **H**, Enter | A short "How DA works" help, and a list of commands | ☐ |
| B7 | Press **U**, Enter | The user guide opens in the browser | ☐ |
| B8 | Press **x** (not a menu key), Enter | "Pick one of the numbers or letters shown." and the menu again | ☐ |
| B9 | Press **Q**, Enter | The menu closes; the window stays open with a line saying you can type `da` for the menu | ☐ |
| B10 | Type `da` in that window | The menu again, starting with the Status | ☐ |
| B11 | Press **7** (New archive), Enter | "Archives on this PC already:" with `jane-archive-202x … <- open now`, then a question for a new folder | ☐ |
| B12 | Type `C:\DA-test\sam-archive-200x`, Enter; years `2000-2009`, Enter | "Archive ready", and the menu now shows **sam-archive-200x** with its Status | ☐ |
| B13 | Press **6** (Switch archive), Enter | Both archives listed with their years; type the number of **jane-archive-202x** | ☐ |
| B14 | | The menu shows jane-archive-202x again, with its Status | ☐ |
| B15 | Press Q. In the same window type `da archives` | A table of this PC's archives (name, years, folder) | ☐ |
| B16 | `da archives --open 2` | The second archive's menu opens (press Q to leave) | ☐ |
| B17 | `da setup C:\DA-test\sam-archive-200x --years 2000-2009` again | It says the archive is already there and keeps its settings (nothing moved) | ☐ |
| B18 | Make a folder `C:\DA-test\filled`, copy 3 kit photos into it, then `da setup C:\DA-test\filled` | It lists what's in the folder and asks before moving those into `intake\`; answer **n** | ☐ |
| B19 | Run it again and answer **y** | The 3 photos are now in `C:\DA-test\filled\intake\`, and the archive's files appear | ☐ |
| B20 | `da setup C:\DA-test\bad --years 1999-1990` | A clear message that years must look like 1990-1999 (nothing made) | ☐ |

## C. The first run: process intake (menu 1)

Copy the whole test kit (except `old`) into `jane-archive-202x\intake\photos\kit` (so `kit\phone`,
`kit\camera`, … are inside), copy `scans` into `intake\scans`, and `docs` into `intake\docs`.

| # | Do this | You should see | Result |
|---|---|---|---|
| C1 | Open jane-archive-202x (its `Open DA.cmd`) | The Status shows the intake files, folder by folder, with counts | ☐ |
| C2 | Press **1** (Process intake) | "Counting what's in intake …", then a list of intake's folders with file counts | ☐ |
| C3 | Type the number of `photos` to open it | Its subfolders (`kit`) are listed; you can open further, go up, or filter by name | ☐ |
| C4 | Type part of a name (for example `kit`) to filter | Only matching folders are listed | ☐ |
| C5 | Go back up to the top of intake and choose to process **all of intake** | "Processing … DA asks before moving anything" | ☐ |
| C6 | Watch step **1/7 Indexing** | A count of files indexed, no error | ☐ |
| C7 | Step **2/7 Hashing** | A progress count, then a summary | ☐ |
| C8 | Step **3/7** (duplicates): it asks whether to set exact copies aside; answer **y** | The 3 `doubles` are listed and moved to `_duplicates-holding` (see F) | ☐ |
| C9 | Step **4/7 Preview** | "planning names and folders (nothing moves)" and a plan: how many files to file, how many need review | ☐ |
| C10 | Step **5/7 Plan/check** | Numbers of files to file, raw files and Live Photo videos going with them, and problems to review | ☐ |
| C11 | It asks whether to file them; answer **n** | It stops; nothing was moved; the run is recorded in `output\runs\` | ☐ |
| C12 | Press **1** again and process all of intake again; answer **y** to each question | Steps 1-7 run; "Filed N; unchanged N (M re-hashed); problems: 0" and "Done. Run record: …" | ☐ |
| C13 | | Right after, "Where things stand now:" and the Status (fewer files waiting) | ☐ |
| C14 | In File Explorer open `photos\organized` | Year folders (`2021`, …) with month folders (`2021-06`, …) | ☐ |
| C15 | Open a month folder | Files named `photo_YYYYMMDD_HHMMSS_xxxx.jpg` (or `.heic`) in date order, each with a `.meta.json` beside it, and a `_contact-sheet.pdf` | ☐ |
| C16 | Check one photo's name against when it was taken (its date in the Photos app) | The date and time in the name match | ☐ |
| C17 | Open one `.meta.json` in Notepad | A text file with `"schema": {"name": "mindit.sidecar", "version": 2}`, a `file` block with its sha256, and a `camera` block | ☐ |
| C18 | Look in `intake\photos\kit` | Only files that need you are left (no date, other decade, …) | ☐ |
| C19 | Back in the menu, press **2** (Status) | Organized photos/documents counts and the last run's time and "filed N" | ☐ |
| C20 | Process intake a third time | "Nothing to file" (or only the review ones are planned) - nothing is filed twice | ☐ |

## D. What needs review (menu 3)

| # | Do this | You should see | Result |
|---|---|---|---|
| D1 | Press **3** | Groups of what the last run left, each with a reason and up to 5 examples | ☐ |
| D2 | | **No date (in the file or its name)**: your scans of prints and any undated files | ☐ |
| D3 | | If you included a photo from another decade in `kit`: **Taken outside this archive's years** | ☐ |
| D4 | | "Full list: …\review.csv" | ☐ |
| D5 | Open that `review.csv` (double-click; it opens in Excel or Notepad) | One row per file: reason, file, detail | ☐ |
| D6 | The screenshot from `other` | Filed by a date in its name, or listed under No date - not a crash | ☐ |
| D7 | The raw file (`.CR2`/`.NEF`) | Moved and renamed together with its JPG (same new name, raw extension), not left alone | ☐ |
| D8 | A raw file whose JPG isn't there | Left in intake | ☐ |

## E. Status and the index (menu 2, 5)

| # | Do this | You should see | Result |
|---|---|---|---|
| E1 | Press **2** | The same numbers as the box at the top, plus intake folder by folder | ☐ |
| E2 | In File Explorer, move one filed photo (and its `.meta.json`) to your Desktop | | ☐ |
| E3 | Press **5** (Refresh index) | It indexes, then the counts drop by one | ☐ |
| E4 | Move the photo back where it was, press **5** | Counts back up | ☐ |
| E5 | Terminal (in the archive): `da db stats` | Counts by year and kind | ☐ |
| E6 | `da db query "SELECT file_name, captured_at FROM files WHERE area = 'photos' LIMIT 5"` | Five photos with their dates | ☐ |
| E7 | `da db query "DELETE FROM files"` | Refused: only SELECT is allowed (nothing deleted) | ☐ |
| E8 | `da status` | The same Status as menu 2 | ☐ |
| E9 | `da intake status` | Intake folder by folder: files, GB, photos, raw, documents, videos, hashed, already in organized | ☐ |

## F. Duplicates and undo (menu 4)

| # | Do this | You should see | Result |
|---|---|---|---|
| F1 | Open `_duplicates-holding` in the archive | Today's date folder with the 3 `doubles` (exact copies), and a `moved.csv` record | ☐ |
| F2 | Press **4** (Undo last set-aside) | "Put 3 files back where they were (from …)?"; answer **y** | ☐ |
| F3 | | "Restored 3"; the doubles are back in `intake\photos\kit\doubles` | ☐ |
| F4 | Process intake again (menu 1, answer y) | The doubles are set aside again (they're still exact copies of filed photos) | ☐ |
| F5 | Press **4** and answer **n** | Nothing changes | ☐ |
| F6 | Delete the folder in `_duplicates-holding` yourself (they're copies) | Fine: DA doesn't need them | ☐ |
| F7 | *(Optional, long paths off: skip it if A4c turned them on)* Put a copy of a kit photo in intake inside folders nested deep enough that its path is about 240 characters, and process intake | The step carries on; *Not moved ... path too long for Windows* for that copy, which stays in intake | ☐ |

## G. Documents and scans

| # | Do this | You should see | Result |
|---|---|---|---|
| G1 | Open `documents\organized` | Year/month folders with `doc_YYMMDD_HHMMSS_xxxx.pdf` (and your Word/Excel file) | ☐ |
| G2 | Compare a PDF's folder with the date it was created (File, Properties in a PDF reader) | It's filed by the date inside the PDF | ☐ |
| G3 | The scans you put in `intake\scans` | Treated as **documents**, not photos; scans with no date wait under No date | ☐ |
| G4 | A PDF with flaws (an old scanner's PDF, if you have one) | Processed without a stream of red/yellow warnings on the screen | ☐ |
| G5 | Put a `.jpg` scan of a letter in `intake\docs` and process | It's filed under `documents`, not `photos` | ☐ |

## H. Contact sheets

| # | Do this | You should see | Result |
|---|---|---|---|
| H1 | Double-click a month's `_contact-sheet.pdf` | Page 1 is a **summary**: folder name, photo/video counts, the days, GPS count, places, sidecar versions, and a **Cameras** table with page numbers | ☐ |
| H2 | Page 2 onwards | A section per camera: each page headed `<month> - <camera> / <owner>` (or just the camera) | ☐ |
| H3 | | 12 pictures a page (3 across, 4 down), each with its name and date underneath | ☐ |
| H4 | A photo taken outdoors with a phone | **GPS** in green down its left edge | ☐ |
| H5 | Every picture | A small circled **2** at its top right (the sidecar version) | ☐ |
| H6 | A video | A dark **VIDEO** tile with its length | ☐ |
| H7 | A Live Photo | Shown once (its photo), not twice | ☐ |
| H8 | Terminal: `da contact-sheets photos\organized --layout 4x5` | "Made or updated N"; that sheet now has 20 pictures a page | ☐ |
| H9 | `da contact-sheets photos\organized` (no layout) | Sheets go back to 3x4 | ☐ |
| H10 | `da contact-sheets photos\organized --layout 9x9` | A clear message: a layout looks like 3x4 or 4x5 | ☐ |
| H11 | Run H9 again | "already up to date N" (nothing made again) | ☐ |
| H12 | Copy one more photo into a month folder (with no sidecar) and run `da validate <that month folder>` | Its contact sheet is made again and includes the new photo | ☐ |
| H13 | `da contact-sheets photos\organized --force` | Every sheet made again | ☐ |
| H14 | In `da-archive.yaml` set `contact_sheets:` `layout: 4x5`, save, run H9 | Sheets now 20 a page; set it back to `3x4` afterwards | ☐ |

## I. Videos, Live Photos and HEIC

| # | Do this | You should see | Result |
|---|---|---|---|
| I1 | Your ordinary videos | Filed in their month as `video_YYYYMMDD_HHMMSS_xxxx.mov` (or `.mp4`) beside the photos | ☐ |
| I2 | Open a video's `.meta.json` | A `video` block with `duration_seconds` and `recorded_at`; `classification` says `video` | ☐ |
| I3 | A Live Photo (HEIC + MOV with the same name) | Both filed together: `photo_…_xxxx.heic` and `photo_…_xxxx.mov` (same name) | ☐ |
| I4 | Copy a Live Photo's `.MOV` alone (without its photo) into intake, process | It stays in intake (it's the short video of a Live Photo) | ☐ |
| I5 | Terminal: `da pair-movies` | It finds that video's filed photo and lists where it would go; nothing moves | ☐ |
| I6 | `da pair-movies --apply` | "Moved 1" and an Undo line; the video is now beside its photo with the same name | ☐ |
| I7 | `da intake undo "<the file it names>"` | The video goes back to intake | ☐ |
| I8 | An old camera `.AVI`/`.MPG` | Filed by the date inside it, or listed under No date (then see J) | ☐ |
| I9 | `da heic-to-jpg photos\organized\<year>\<month>` | JPG copies of the HEIC photos made in a folder beside it (the HEICs stay) | ☐ |
| I10 | `da heic-to-jpg <a folder> --out C:\DA-test\jpgs` | The copies go to `C:\DA-test\jpgs` | ☐ |

## J. Fix dates (menu D)

| # | Do this | You should see | Result |
|---|---|---|---|
| J1 | Press **D** | Each intake folder with undated photos, one at a time, with a count and an example name | ☐ |
| J2 | For the scans folder type `1998-07`, Enter | (B1's archive takes 2020-2029, so these will wait as "outside this archive's years" - that's expected) | ☐ |
| J3 | For another folder type `July`, Enter | "'July' isn't a date DA reads. Use 1998, 1998-07, …" and it asks again | ☐ |
| J4 | Type `2021-06-15`, Enter | Accepted | ☐ |
| J5 | Press Enter on a folder | That folder is skipped | ☐ |
| J6 | | "Dates set on N files." and "Process intake now?"; answer **y** | ☐ |
| J7 | | The folder dated 2021-06-15 is filed as `photo_20210615_000000_xxxx` in `2021\2021-06` | ☐ |
| J8 | Terminal: `da date list` | Photos still without a sure date, folder by folder (or "Every photo … has a sure date") | ☐ |
| J9 | `da date set "<a scan>" --date 2022` | "Only a year: DA files them under 2022-01 (January)…", "Date set to 2022 on 1 file" | ☐ |
| J10 | `da date set "<a scan>" --date "2022-03-04 14:30"` | Date set; after processing, named `photo_20220304_143000_…` | ☐ |
| J11 | `da date set "<a scan>" --date 2022-13` | A clear message: not a real date | ☐ |
| J12 | `da date clear "<that scan>"` | "Dates set by hand taken off on 1 file" | ☐ |
| J13 | Pick a **filed** photo; `da date shift "<it>" --by +1h` | "Dates shifted +1h on 1 file" and a `da validate … --mode repair` line | ☐ |
| J14 | Run that `da validate … --mode repair` line | The photo is renamed one hour later (and moved if the month changed) | ☐ |
| J15 | `da date shift "<it>" --by -1h` and repair again | Back to its original name | ☐ |
| J16 | `da date shift <folder> --by +2d` / `-30m` / `+1mo` / `-1y` | Each accepted (try one, then shift back) | ☐ |
| J17 | `da date shift <folder> --by 1h` (no sign) | A clear message: use +1h, -30m, … | ☐ |
| J18 | Shift a folder that includes an undated scan | The undated one is listed as skipped: "no sure date to shift" | ☐ |

## K. Tags (terminal)

| # | Do this | You should see | Result |
|---|---|---|---|
| K1 | In the archive: `da tag` | "Read camera details and make automatic tags for N photos in …?"; answer **y**; "Tagged N photos" | ☐ |
| K2 | Open a filed photo's `.meta.json` | `auto_tags` with tags like `maker:apple`, `camera:apple-iphone-…`, `year:2021`, and `gps` for outdoor photos | ☐ |
| K3 | `da tag --cameras` | A table of the cameras found, with photo counts and years; it asks who used each (type a name like `jane`, or Enter to skip) | ☐ |
| K4 | | "saved: <camera> -> jane", and `da-archive.yaml` now has that camera under `cameras:` (a `.bak` copy kept) | ☐ |
| K5 | `da tag --owner "<a camera from K3>" sam` | "saved: … -> sam" and "Update the owner: tags now?" | ☐ |
| K6 | `da tag photos\organized\<year>\<month> beach` | "Your tags on N files: +beach" | ☐ |
| K7 | `da tag photos\organized\<year>\<month> -x beach` | "-beach" | ☐ |
| K8 | `da tag "<one photo>" grandma "summer trip"` | Tags `grandma` and `summer-trip` added to that photo | ☐ |
| K9 | `da findit tags photos\organized -r grandma -v` | `"match_count": 1` and that photo | ☐ |
| K10 | `da findit tags photos\organized -r gps -v` | The photos with a location | ☐ |
| K11 | `da findit tags photos\organized -x gps -v` | The photos without | ☐ |
| K12 | `da findit tags photos\organized -r owner:jane -v` | Photos from the camera you named in K3 | ☐ |
| K13 | `da tag --refresh` (answer y) | Camera details read again from every photo; tags unchanged | ☐ |
| K14 | Open a contact sheet made after K3 (run `da contact-sheets <month>`) | The camera sections now show **/ jane** | ☐ |
| K15 | Copy 2-3 screenshots or photos of receipts into `intake\phone` and choose **1 Process intake** | They're filed under `photos\organized` | ☐ |
| K16 | `da tag ocr photos\organised` (a typo) | *No such folder or file*; nothing is tagged | ☐ |
| K17 | `da tag ocr photos\organized\<their year>` | A preview: how many are mostly text (document), with some text, without; *Nothing changed*; the path of `ocr-results.csv` | ☐ |
| K18 | Open that `ocr-results.csv` in Excel | One row per picture: level, words, *would tag and move* for the screenshots, and the start of their text | ☐ |
| K19 | `da tag ocr photos\organized\<their year> --tag-only` | *read now: 0* (the preview's reading is reused); *Tagged N pictures* | ☐ |
| K20 | Open a screenshot's `.meta.json` | An `ocr` block with its text, and `text`, `document` in `auto_tags` | ☐ |
| K21 | `da tag ocr photos\organized\<their year> --tag-and-move` | It asks *Move N document pictures?*; answer **y**: they're in `documents\organized\<year>\<year-month>` with `doc_` names, with sidecars | ☐ |
| K22 | `da intake undo "<the ocr-moved.csv it printed>"` | They're back in `photos\organized`, with their old names | ☐ |
| K23 | `da rename` | *0 would be renamed, N already named so*; *Nothing changed*; the path of `rename-plan.csv` | ☐ |
| K24 | `da rename photos\organized\<their year> --pattern "{YYYY}{MM}{DD}_{camera}_{owner}_{hash:4}"` | How many *would be renamed*, raw files following them, and *had nothing for {owner}* for photos with no known owner; the files keep their names | ☐ |
| K25 | Open that `rename-plan.csv` in Excel | One row per file: its path, the new name, *rename* / *follows* / *unchanged*, and notes like *the name token {owner} was missing* | ☐ |
| K26 | `da rename intake` | *use da run*; nothing is planned | ☐ |
| K27 | In the menu press **N** | The photo, video and document patterns, and how to try one | ☐ |
| K28 | Type **1**, then the pattern `{YYYY}-{MM}-{DD}_{hh}{mm}_{hash:4}` | How many *would be renamed*; *Rename N files?* - answer **y** | ☐ |
| K29 | | *Renamed N*, and an *Undo: da intake undo ...* line; then *Save it in da-archive.yaml?* - answer **y** | ☐ |
| K30 | Open a month folder and `da-archive.yaml` | Photos named like `2024-07-04_1015_ab12.jpg` (raw files too, sidecars beside them); in the file, the new pattern and `# was (<today>): photo_...` under it | ☐ |
| K31 | Press **N** again, then **Enter** | *0 would be renamed* | ☐ |
| K32 | `da intake undo "<the rename-moved.csv it printed>"` | The old names are back; **N**, **Enter** now offers to rename them again (the saved pattern stays until you change it) | ☐ |
| K33 | Press **N**, **1**, type the old pattern (`photo_{date_taken:%Y%m%d_%H%M%S}_{hash:4}`), answer **y** twice | Back as before; `da-archive.yaml` keeps both earlier patterns as notes, newest first | ☐ |
| K34 | `da rename --folder "{owner}\{YYYY}"` | *N moved to another folder*, *had nothing for {owner}* for photos with no known owner; nothing moves | ☐ |
| K35 | `da rename --folder "{owner}\{YYYY}" --kind photo --apply --save` and answer **y** twice | Photos of cameras with an owner are in `photos\organized\<owner>\<year>`, the others in `photos\organized\<year>`; the emptied month folders are gone; each folder has a contact sheet | ☐ |
| K36 | Copy a new photo into intake and choose **1 Process intake** | It's filed by the new folder pattern | ☐ |
| K37 | `da intake undo "<the rename-moved.csv it printed>"`, then **N**, **1**, Enter, type `{YYYY}\{YYYY}-{MM}`, answer **y** twice | Back in year and month folders; `da-archive.yaml` keeps `# folder was (...)` notes | ☐ |
| K38 | *(Optional: do it between K35 and K37, while the photos are in the owner layout)* `da location group <a month with GPS photos, e.g. 2024-07>` and give group 1 a title | The month's photos are found in `<owner>\<year>`; the location folder is made there (`<owner>\<year>\<year-month> <title> (<place>)`) | ☐ |

## L. Places and location folders (menu L)

These need an internet connection, except L12.

| # | Do this | You should see | Result |
|---|---|---|---|
| L1 | Terminal: `da location lookup` | How many photos have a GPS position, how many new places, "about one a second", a privacy note; "Start?" | ☐ |
| L2 | Answer **y** | A progress count, then "N of N GPS photos have a place" and a list like `place:springfield-il  24` | ☐ |
| L3 | Run it again | "0 new spots"; it finishes at once (places are remembered) | ☐ |
| L4 | `da findit tags photos\organized -r place:<one of the places> -v` | Those photos | ☐ |
| L5 | `da db query "SELECT city, COUNT(*) FROM files GROUP BY city"` | Towns with counts | ☐ |
| L6 | In the menu press **L** | "Months with GPS photos (newest first):" numbered | ☐ |
| L7 | Type a month's number | Groups of photos taken close together: count, days and times, places, first file | ☐ |
| L8 | For group 1 type a title like `Beach day`; press Enter for the others | "DA will: make  2021-06 Beach day (<place>)   (N photos)" and "Move them?" | ☐ |
| L9 | Answer **y** | "Moved N photos into 1 folder; … contact sheets made" and an **Undo** line | ☐ |
| L10 | Open the year folder | `2021-06 Beach day (<place>)` beside `2021-06`, with its own contact sheet; photos without GPS stayed in `2021-06` | ☐ |
| L11 | `da validate "photos\organized\2021\2021-06 Beach day (<place>)"` | "Problems found: 0" (a location folder is a proper home) | ☐ |
| L12 | `da location rename "<that folder>" "Beach with grandma"` | The new name, "Rename it?", then "Renamed; title set on N sidecars" and an Undo line | ☐ |
| L13 | `da location set "<a photo without GPS>" --place "Springfield, IL"` | "Found: Springfield, …", asks, "Done: 1 photo" | ☐ |
| L14 | `da location set "<another photo>" --same-as "<a GPS photo>"` | "Done: 1 photo" (no lookup) | ☐ |
| L15 | `da location set "<that photo>" --clear` | "Done: 1 photo" | ☐ |
| L16 | Group that month again with **L** | A group taken at the same time and place says "fits the folder already there"; Enter adds to it | ☐ |
| L17 | `da location group photos\organized\<year>\<month> --hours 1 --km 0.5` | Smaller groups; answer **n** / press Enter to move nothing | ☐ |
| L18 | `da intake undo "<the file L9 named>"` | The photos go back to `2021-06`; the location folder is gone | ☐ |
| L19 | `da location lookup --offline` | Uses only remembered places; nothing sent | ☐ |
| L20 | In `da-archive.yaml` set `location:` `lookup: off`, run `da location lookup` | "Lookups are off in da-archive.yaml …"; set it back afterwards | ☐ |
| L21 | `da location group C:\DA-test` (not a month folder) | A clear message that it isn't a month folder | ☐ |

## M. Split by years (menu S)

Copy the kit's `old` photos (another decade) into jane-archive-202x's `intake\photos\old`, process intake
(they stay: outside this archive's years). sam-archive-200x (from B12) takes 2000-2009.

| # | Do this | You should see | Result |
|---|---|---|---|
| M1 | In jane-archive-202x press **S** | "Working out the dates …", "N files in intake were taken outside 2020-2029", and which archive each belongs in | ☐ |
| M2 | | "Move them to:" with sam-archive-200x listed; choose it | ☐ |
| M3 | | What will move (from → to) and "Move them?"; answer **y** | ☐ |
| M4 | | "Moved N files", an Undo line, and "Next: open sam-archive-200x … 1 Process intake" | ☐ |
| M5 | Open sam-archive-200x's `intake\photos\from-jane-archive-202x` | The old photos (and their sidecars) | ☐ |
| M6 | In sam-archive-200x, process intake | They're filed in `2000s` year folders | ☐ |
| M7 | Terminal (jane-archive-202x): `da split` | "0 files in intake were taken outside 2020-2029" | ☐ |
| M8 | Undo instead (repeat M1-M4 with new old photos, then `da intake undo "<the file M4 named>"`) | They're back in jane's intake (works even across drives) | ☐ |
| M9 | A decade with no archive yet | "N from the 1990s have no archive on this PC yet. Make one: da setup <folder> --years 1990-1999" | ☐ |
| M10 | Make an archive with no years (`da setup D:\test-all --yes`), copy photos from two decades into its intake, process it | They're filed in its `photos\organized` | ☐ |
| M11 | In it: `da split --organized` | *N filed files were taken with a sure date*, and how many belong in each decade's archive | ☐ |
| M12 | `da split --organized --to <one decade's archive>`, answer **y** | *N straight into its organized folders*; *Moved N files*; the photos are in that archive's `photos\organized\<year>\<year-month>` with sidecars and a contact sheet, and gone (with their emptied folders) from the first | ☐ |
| M13 | Open that archive and choose **2 Status** | The photos are counted there (its index was updated) | ☐ |
| M14 | `da intake undo "<the split-moved.csv it printed>"`, then **5 Refresh index** in both | They're back in the first archive | ☐ |
| M15 | Make an archive and merge another into it (`da merge --from <the other>` in the new one); then, in a terminal outside both: `da archives delete <the other>` | *N have a copy elsewhere*, *Everything ... also exists elsewhere*, *Type the archive's name*; press **Enter**: *Kept* | ☐ |
| M16 | Copy one new photo into the other archive's `intake\photos`, then `da archives delete <the other>` again | *Not deleted: 1 files exist only in ...*, with that photo listed | ☐ |
| M17 | Delete the new photo; `da archives delete <the other>` and type its name | It's in the Recycle Bin, and gone from `da archives` | ☐ |
| M18 | Restore it from the Recycle Bin; open its `Open DA.cmd` | It's back on `da archives` | ☐ |

## N. Merge two copies (menu M)

Copy the whole `C:\DA-test\jane-archive-202x` folder to `C:\DA-test\jane-copy`. Add 3 new photos to
jane-copy's intake and process them **in jane-copy** (open its `Open DA.cmd`).

| # | Do this | You should see | Result |
|---|---|---|---|
| N1 | In **jane-archive-202x** press **M** | This PC's other archives listed; choose jane-copy (or type its folder) | ☐ |
| N2 | | "Indexing …", "Comparing …", "N files in jane-copy: M already here" and what would be copied (3 to the same folder and name here) | ☐ |
| N3 | | "Copy them?"; answer **y** | ☐ |
| N4 | | "Copied 3 files: 3 filed …" and an Undo line; the 3 photos are in jane-archive-202x's month folders | ☐ |
| N5 | Look in jane-copy | Unchanged (merge only copies from it) | ☐ |
| N6 | Press **M** again, choose jane-copy | "Nothing to copy" | ☐ |
| N7 | `da intake undo "<the file N4 named>"` | The 3 copies are removed from jane-archive-202x | ☐ |
| N8 | `da merge --from C:\DA-test\nowhere` | A clear message that it isn't an archive | ☐ |

## O. Report and dashboard (menu R, B)

| # | Do this | You should see | Result |
|---|---|---|---|
| O1 | Press **R** | A short summary, then the PDF opens | ☐ |
| O2 | | One page: what's filed (photos, documents, videos, space, years), waiting for you, by year, cameras, places | ☐ |
| O3 | Open the archive's `output` folder | `jane-archive-202x-report-YYYY-MM-DD.pdf` | ☐ |
| O4 | `da report --refresh` | The index is refreshed first; the same day's PDF is replaced | ☐ |
| O5 | `da report --open` | The PDF opens | ☐ |
| O6 | Press **B** | The browser opens a page titled *DA - jane-archive-202x*; DA says how to stop it (`da dashboard --stop`) and the menu is back straight away | ☐ |
| O7 | | **Filed**, **Waiting in intake** (folder by folder), **Needs review**, **Latest runs** and **Activity** match what you've done so far | ☐ |
| O8 | Wait a few seconds | **In the archive** fills in: by year, cameras, places (the same numbers as the report) | ☐ |
| O9 | Copy a few photos into `intake\photos`, then in another window `da db build` | Within about 10 seconds the page shows the new files waiting; while `da db build` runs, **Happening now** names it | ☐ |
| O10 | Press **Recount** | The button greys out, then the numbers are counted again | ☐ |
| O11 | Press **B** again | *already running*, with the same address; the same page opens (not a second dashboard) | ☐ |
| O12 | Quit the menu and close its window; reload the page | The dashboard still works | ☐ |
| O12a | In a terminal in the archive, `da dashboard --stop` | *Dashboard stopped*; after a few seconds the page says the dashboard stopped | ☐ |
| O12b | `da dashboard --stop` again | *No dashboard is running for this archive* | ☐ |
| O12c | `da dashboard --foreground --port 9000` | It prints `http://127.0.0.1:9000/` (or the next free port) and the browser opens it; **Ctrl+C** stops it | ☐ |
| O13 | From another computer or a phone, try this PC's name or address with that port | It doesn't open: the dashboard is for this PC only | ☐ |

## P. Update sidecars (menu J)

| # | Do this | You should see | Result |
|---|---|---|---|
| P1 | Press **J** | "N sidecars: N up to date (schema 2), 0 older." (everything DA made is current) | ☐ |
| P2 | *(If you have an older DA archive)* run J there | How many are older and what would change, then "Upgrade N sidecars?" | ☐ |
| P3 | Answer **y** | "Upgraded N sidecars", the backup folder, and a `--restore` line | ☐ |
| P4 | Run the `--restore` line | "Put back N sidecars" | ☐ |
| P5 | `da sidecar upgrade photos\organized\<year>` | Only that year is looked at | ☐ |

## Q. Checking what's filed (terminal)

| # | Do this | You should see | Result |
|---|---|---|---|
| Q1 | `da validate photos\organized` | A summary: files checked, problems found (0 or a few notes), nothing moved | ☐ |
| Q2 | Rename a filed photo in Explorer to `test.jpg` (keep its `.meta.json` renamed to match: `test.jpg.meta.json`), then `da validate <its folder>` | A "wrong name" problem for it, nothing moved | ☐ |
| Q3 | `da validate <its folder> --mode repair` | It's renamed back to `photo_…` | ☐ |
| Q4 | `da validate intake --mode repair` | Refused: repair isn't for intake (use 1 Process intake / `da run`) | ☐ |
| Q5 | `da validate C:\DA-test\kit-copy --archive C:\DA-test\jane-archive-202x` (any folder outside) | It checks that folder using jane's settings | ☐ |
| Q6 | `da run intake\photos\kit\camera --yes` | That folder alone is processed, no questions | ☐ |
| Q7 | `da check "<the preview report path from a run>"` | A check of that report | ☐ |
| Q8 | `da verify "<a repair report path>"` | Quick: every filed file in place with its size and date, a sample re-hashed; *ok* | ☐ |
| Q8a | `da verify "<a repair report path>" --full` | Every filed file re-read; its hash matches its sidecar (slower) | ☐ |

## R. Settings (da-archive.yaml)

Make a copy of `da-archive.yaml` first; put it back at the end.

| # | Do this | You should see | Result |
|---|---|---|---|
| R1 | Change `years:` to `"2021-2021"`, process a folder with 2022 photos | They wait as "outside this archive's years" | ☐ |
| R2 | Add an intake folder: under `intake:` add `phone: photo`, then `da setup <this archive>` | `intake\phone` is created | ☐ |
| R3 | Change `photoit:` `pattern:` to `{date_taken:%Y-%m-%d}_{hash:4}` and validate a month with `--mode repair` | Photos renamed like `2021-06-01_ab12.jpg` (change it back and repair again) | ☐ |
| R4 | Break the file (delete a `:`), then `da status` | A clear message about da-archive.yaml (no crash) | ☐ |
| R5 | Put the copy back, then `da status` | The Status as before | ☐ |

## S. Logs, records and safety

| # | Do this | You should see | Result |
|---|---|---|---|
| S1 | Open `logs\da.jsonl` in Notepad | One line per command: "da … started", "… finished in Ns", and lines for what was moved | ☐ |
| S2 | Open `output\runs\` | A folder per run (`…-run`, `…-split`, `…-merge`, `…-location-group`, …) with its records | ☐ |
| S3 | Start processing a big folder and press **Ctrl+C** during step 2 | It stops; run it again and it carries on (nothing half-moved) | ☐ |
| S4 | Run `da run --yes` in one window and `da status` in another | Status works while the run is going (don't run two changing commands at once - see the known problems) | ☐ |
| S5 | Throughout: did DA ever delete a photo? | No (it only moves, and asks first) | ☐ |

## T. Another PC or a USB drive

| # | Do this | You should see | Result |
|---|---|---|---|
| T1 | Copy `C:\DA-test\sam-archive-200x` to a USB stick | | ☐ |
| T2 | On another PC with DA installed (or the same one, from the stick), double-click the stick's `Open DA.cmd` | The menu opens for that archive | ☐ |
| T3 | `da archives` | The stick's archive is now on this PC's list | ☐ |
| T4 | Unplug the stick, `da archives` | It's left out until it's plugged in again | ☐ |

## U. Messages when something's wrong

| # | Do this | You should see | Result |
|---|---|---|---|
| U1 | `da run` in `C:\` (not an archive) | "Not inside an archive …" and how to open one | ☐ |
| U2 | `da tag photos\organized\2099\2099-01` (a folder that doesn't exist) | *(Known problem: it's treated as a tag. See the known problems; undo with `da tag --remove photos-organized-2099-2099-01`.)* | ☐ |
| U3 | `da location set <a photo> --place "zzzz nowhere"` | "Nothing found for …" | ☐ |
| U4 | Disconnect the internet, `da location lookup` on new GPS photos | It stops after two tries and says N photos still need a place; run again later | ☐ |
| U5 | `da contact-sheets C:\nowhere` | "No such folder" | ☐ |
| U6 | `da --help` and `da location --help` outside an archive | Help shows (no "not inside an archive") | ☐ |

## V. Clean up

| # | Do this | You should see | Result |
|---|---|---|---|
| V1 | Delete `C:\DA-test` and `C:\DA-test-kit` when you're done | (Your real photos were never touched) | ☐ |
| V2 | To remove DA: delete `C:\Scripts\DA`, and remove it from your PATH (Settings, search "environment variables", Path) | `da` is no longer recognised | ☐ |

## Reporting a problem

1. Check the [known problems](https://da.gamenightbymike.com/defects.html) first.
2. On the website, press the step's **Report** button: a new issue opens at GitHub with the step, your name and
   your version filled in (a free GitHub account is needed). Or open one yourself at
   https://github.com/devmukmuk/DA/issues, or send it to the person who asked you to test. The panel at the top
   shows how many of your reports are still open.
3. Include: the step number (**L9**), what you did, what you expected, what happened (a screenshot helps),
   your DA version (`da version`), and whether DA is the DA.exe or the Python install.
4. If DA printed an error, the archive's `logs\da.jsonl` has the details: copy the last few lines.
5. Leave out anything private: names, photos, and folder paths you'd rather not share.
