# Changelog

What changed in each release of TNF Tools. The newest is first. Installers for every version
are on the [Releases](../../releases) page.

## 1.0.10

### Added

- **Intel channel alerts.** A report in one of your intel channels is read out when it names a
  confirmed neutral within jump range of one of your characters. The range is set under
  Intel → Settings and defaults to 3 jumps; a "clr" for a system silences it.
- **A voice button in the top bar** pauses and resumes spoken and tone alerts without touching
  the thumbnail HUD, the toasts or the log.
- **Intel → Notifications** lists the Intel alerts on their own page.
- **Hold to move a preview.** Thumbnails need a short hold before they drag, so a click to focus
  a client no longer nudges its preview. The hold time is under Preview → Settings.
- **Edge layouts for the in-game KPI cards.** Auto-arrange can stack the cards against the left
  or right edge, or run them along the top or bottom, as well as lay out a grid.
- **A switch for showing each character's system on their thumbnail** (Intel → Settings). The
  setting existed, with a description, but had no control.

### Changed

- **One watch control, in the top bar.** The button there now starts DPS watching, pauses
  everything and resumes it. The separate Start/Stop watching button on the DPS page is gone.
  Bounty sessions still start and end on the Bounty page.
- **DPS Master's overview is easier to read.** One status bar says whether DPS is watching,
  paused or off, and whose numbers are showing. Characters that have fought appear as chips,
  busiest first; click one to see only that character. With nothing recorded yet, the page says
  so instead of showing panels of zeros. "Parse combat lines" moved to DPS → Settings.
- **Moving and arranging the in-game KPI cards is on DPS → Characters**, next to each
  character's layout, and the page names the hotkey that unlocks the cards.
- **In-game KPI cards are one fixed width**, Full and Compact alike, and show whole-number rates
  with room for four digits each way. Auto-arrange tiles them edge to edge with only the gap
  you set.
- **Hotkeys are shown as you press them** ("Ctrl+Shift+K"), not in their stored form.
- **A consistency pass over every page**: one spelling, sentence-case headings, themed links,
  clearer wording on the Modules page, and empty panels that no longer take up a screen.

### Removed

- **The "Paste D-scan link" hotkey.** It pasted a link into the focused client's chat and never
  worked reliably. D-scans still upload when you copy them; copy the link from Intel → Reports.
  The app sends no input to the EVE client.

### Fixed

- **Watch status that disagreed with itself.** While paused, the top bar said "Not watching",
  the DPS page said it was watching, and the menu showed a character count. Every place that
  shows a watch state now shows the same one of three: Watching, Paused or not watching.
- **Dashboard cards stuck on their first status.** A card's badge updated once and then never
  again.
- **Hold-to-move on a thumbnail often did nothing.** The hold was abandoned whenever the
  preview window lost focus. It now only ends when you let go, and the cursor shows the hold
  and the release.
- **Click-through on thumbnails did not survive a restart.** The setting stayed on, but new
  preview windows ignored it.
- **The DPS graph's time axis** showed bucket numbers under a "minutes" label. It now shows
  minutes.
- **Overlapping column headings** on the Preview slots table, and an arrangement list cut off
  on the Auto-arrange page.
- **A background task could stop at startup** if a log line arrived in the first moment after
  launch, leaving alerts or tracking silent until the next restart.
- **Energy-neutraliser alerts for your own neutralisers.** The alert now needs a combat line
  aimed at you.
- **Intel lines reached the server late** while EVE still had the chat log open.
- **A relogged client took up to a minute to get its preview back.**

## Earlier versions

See the notes on each release on the [Releases](../../releases) page.
