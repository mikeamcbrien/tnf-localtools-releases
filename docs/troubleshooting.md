# Troubleshooting

## Installing and updating

**Windows says the publisher is unknown.** Expected: the installer is not code-signed. Choose
**More info**, then **Run anyway**. Compare the file's SHA-256 with the release notes first if
you want to be sure it is the real one.

**The app does not update.** Updates are found about 90 seconds after launch and every six
hours. Check by hand under **Settings → General**. **Settings → Diagnostics** shows the result
of the last check.

**"Update available" and then it fails.** Restart the app and check again. A downloaded update
is held in memory until you restart, so if the app was closed forcibly in between, it has to be
downloaded again.

## Nothing is being tracked

1. **Is the watch button on?** The button at the right of the top bar should read
   **Watching**. If it reads **Paused**, click it. If it reads **Not watching**, click it to
   start DPS watching, or start a session on the Bounty page.
2. **Is the log folder right?** **Settings → Local Configuration** should point at EVE's
   `Gamelogs` folder.
3. **Is EVE writing logs?** Look in that folder for a file with today's date. If there is none,
   switch logging on in EVE's settings.
4. **Is the character switched on?** Check **Bounty → Characters** and **DPS → Characters**.
5. **Is the character muted?** **Settings → Diagnostics → Mute a pilot's logs** lists muted
   characters.

## Previews

**A character has no thumbnail.** Its client has to be running, and the character needs a slot
under **Preview → Preview slots** that is enabled. A client that has just started or logged in
is picked up within a second or two.

**I cannot move a thumbnail.** Hold the left button for the hold time before dragging; the
cursor changes when the thumbnail comes loose. The time is under **Preview → Settings** (3
seconds by default; 0 moves on any drag). If thumbnails do not respond to the mouse at all,
**Click-through** is on: switch it off under **Preview → Overlays**.

**The game stutters in big fights.** Each live thumbnail is redrawn by Windows every frame.
Use **Suspend previews** under **Preview → Settings** to find out whether they are the cause.

**A slot hotkey does nothing.** Something else is using that key combination. Choose another.

## Alerts

**I hear nothing.** Check the voice button in the top bar says **Voice on**, that **Voice /
tone** is switched on under **Settings → Alerts & Notifications → Destinations**, and that the
alert's priority has **Voice / tone** lit in the **Routing** table.

**An alert fires for the wrong characters.** Expand the alert's row and check who it applies to.

**Too many announcements at once.** Raise the **Digest window**, which merges identical alerts
from several characters into one.

## In-game KPI cards

**I cannot drag a card.** Press the move hotkey first (Ctrl+Shift+K by default). The cards
ignore the mouse until then. Cards set to **On thumbnail** follow their thumbnail and cannot be
dragged.

**A card is off the screen.** Use **Auto-arrange** on **DPS → Characters** to bring every card
back.

## Intel

**It says "Not linked".** Open **Intel → Settings** and choose **Link to server**, then approve
the code in the browser tab that opens. You must be signed in on the server's site.

**Reports are not arriving.** Look at the **Outbox** at the bottom of **Intel → Settings**. If
the server is unreachable the reports wait there and are retried; **Retry now** forces a pass.
If the link was rejected, link again.

**A friendly pilot was reported as a neutral.** Open **Intel → Reports** to see how each pilot
in the last capture was classified. Add the corporation or alliance to the friendly lists in
Settings, or mark the pilot friendly under **Intel → Tags**. Linking your characters through
EVE's sign-in lets the app use your contact standings.

**No systems are shown.** Systems come from the Local chat log. Chat logging must be on in EVE,
and a character's system appears after they next jump or undock.

## Reporting a problem

1. **Settings → Diagnostics → Save report.**
2. Open the file and check you are happy to share it: it names your characters and systems.
3. Open an issue on this repository, describe what happened, and attach the report.
