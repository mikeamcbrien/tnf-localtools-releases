# Privacy and data

What TNF Tools reads, what it keeps, and what leaves your computer.

**The short version.** By default nothing about your game leaves your machine. Two features
send data out, and both are off until you turn them on: the optional **Intel** module, and
linking a character through **EVE's own sign-in**.

TNF Tools has no analytics, no telemetry, no crash-reporting service, and no account of its own.

## What it does not do

- It does not read the game's memory.
- It does not modify the game client or its files.
- It does not type or click in the game, and does not play it for you: nothing is targeted,
  fired or warped by the app.
- It does not record, save or transmit what is on your screen.

One thing looks like input and is not. When Windows refuses to bring a client to the front, the
app presses an unassigned key code that no program acts on, so that Windows will allow the
switch. Other preview tools do the same. The game receives no command from it.

## What stays on your computer

| What | How it is used |
|---|---|
| **Game logs** (`...\EVE\logs\Gamelogs`) | Read for bounty payouts, combat lines and the events behind alerts. Their contents are never uploaded by any feature |
| **Chat logs** (`...\EVE\logs\Chatlogs`) | The Local log is read for which character a file belongs to and which system they are in. With the Intel module on, the intel channels you list are also read |
| **Settings, session history and state** | Files in `%APPDATA%\com.tnf.localtools` |
| **The application log** | A rotating file in the same folder, kept so that a bug report has something to attach. It stays on disk unless you send it |
| **Client thumbnails** | Live views from Windows' compositor. Not pictures: nothing is recorded |

Everything the app stores is a file you can read or delete. Deleting
`%APPDATA%\com.tnf.localtools` resets the app.

## What goes out, and when

### Always: update checks

The app asks this repository on GitHub whether a newer version exists, and downloads it if
there is one. Nothing about you is sent; it is a plain download.

### Character portraits

The app shows character portraits and ship icons from CCP's public image service
(`images.evetech.net`).

### Only if you link a character: EVE sign-in and ESI

Linking uses EVE's own sign-in page in your browser. TNF Tools never sees your password. CCP
shows you exactly what is being requested before you approve it:

| Access | Used for |
|---|---|
| Location, ship type, online status | Where each character is and what they are flying |
| Wallet journal | ESS payouts in Bounty Tracker |
| Personal, corporation and alliance contacts | Telling friendly pilots from neutrals |
| Assets, and structure names | Asset lookups |
| Set waypoint | Setting a destination in game when you ask for one |

The sign-in token is kept in the **Windows credential store**, not in a settings file. Unlinking
a character deletes it. You can also revoke access at any time on your EVE account's
third-party applications page, which cuts it off whatever this app does.

Separately, CCP's **public** ESI (no sign-in) is asked for pilots' corporations and alliances
when the Intel module needs to know who is friendly. Nothing of yours is attached to those
requests beyond the names being looked up.

### Only if you turn on the Intel module and link it to a server

The Intel module pairs with a companion server run by your corporation or alliance. Once it is
linked, it sends that server:

- **Intel chat-channel lines** from the channels you list, as your client wrote them, including
  who said them.
- **Local rosters**: pilot names from a Local member list you copied, with the system and the
  character that captured it.
- **D-scans** you copy, with the system.
- **Notes and tags** you write about pilots.
- **The Local channel's chat text**, only if you switch on **Ship Local**. It is off by default.

It also receives from the server: the list of friendly groups, pilots your group is watching,
and waypoints you ask for from the server's website.

What that server does with the data is up to whoever runs it, not this app.

#### The clipboard and two keys

To capture a Local roster or a D-scan, the Intel module reads the clipboard while it is on. It
acts only on clipboard contents that look like a Local member list or a D-scan.

To tell a whole-list copy from a partial one, it also notes when **Ctrl+A** and **Ctrl+C** are
pressed while an EVE client has focus. It checks those keys only, keeps only the time of the
press, and writes none of it to disk. It does not record what you type.

## Diagnostic reports

**Settings → Diagnostics → Save report** writes a file to a place you choose. The app sends it
nowhere. **Open it before you send it to anyone.** It names your characters and the systems
they were in, and includes the end of the application log, which can contain intel. Your
Windows user name is removed from file paths.

## Third-party terms

TNF Tools is a third-party tool for EVE Online. Whether and how you use any third-party tool
with your account is your responsibility under CCP's terms. If you are unsure whether something
is permitted, ask CCP.

## Questions

Open an issue on this repository.
