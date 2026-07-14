# Changelog

## Unreleased

- **Create UI is much faster to design** ? added ready-made controller/dashboard/monitor templates, full color themes, multi-select and group dragging, duplicate, clipboard-free copy/paste, alignment buttons, smart snapping guides, select-all, and multi-delete
- **More ways to make generated controllers look polished** ? pages can have their own icon and accent, controls can use built-in icons and hover tooltips, and loadouts gain a compact tile style alongside choices, buttons, and dropdowns
- **Create UI editor controls stay reachable** ? Save UI and Cancel now reserve their footer space instead of being pushed below the window as the designer grows

---

## v15.64

- **A clearer Studio interface, with a Classic fallback** - refreshed the main window, action list, settings, dialogs, and Mini controls with a more consistent dark style and readable action groups; Settings now lets you switch back to Classic after reopening Macro Studio, while keeping the normal and Mini window sizes unchanged
- **Ended paths can be awakened by jumps again** — if a parallel path naturally finishes, a later jump to that path now restarts its path thread and applies the jump instead of leaving the signal with nobody to consume it

---

## v15.63

- **Locked jumps inside loadouts stay correct** — when folders are combined into a loadout, locked jumps hidden inside each group now resync by action ID, so choosing one group will not accidentally use another group's old jump target

---

## v15.62

- **Jumps inside loadouts can skip later actions now** — if the active loadout group runs a Jump, Macro Studio now passes that jump back to the parent path so it can skip another top-level action/loadout like a normal jump

---

## v15.61

- **Copied locked jumps stay inside the pasted copy** — when you copy/paste multiple actions together, locked jump targets now remap to the matching pasted action instead of staying locked to the original action
- **Limit tries can lock its target action** — Image / color detect's Limit tries "Go to specific" target now has the same lock checkbox as normal jump targets
- **Tap-to-pick everywhere in Discord** — bare `!ms load` posts your saved macros as a tap-to-pick list (tap a number to load), bare `!ms speed` and `!ms loop` post common values to tap, and `!ms play <name>` loads a saved macro and plays it in one command — full remote control without typing names
- **Build macros from Discord** — `!ms new` starts a blank macro instantly (no save prompt), `!ms add click 640 480` / `move` / `key` / `hotkey` / `text` / `wait` appends steps, and `!ms undo` reverts a mistake
- **Find screen coordinates from your phone** — `!ms shot grid` sends a screenshot with a labeled coordinate grid, and `!ms zoom 640 480` sends a magnified close-up with a crosshair and fine grid so you can pinpoint the exact pixel before adding a click

---

## v15.60

- **Tap-to-pick loadouts from Discord** — `!ms loadout <step>` now posts the loadout's groups with number reactions: tap 1️⃣/2️⃣/3️⃣ on your phone and that group becomes active, with a confirmation message. `!ms loadout show` lists every loadout and where it lives, `!ms loadout 2` opens the picker for Path 2's loadout, and the old direct form (`loadout 12 Farm`) still works

---

## v15.59

- **Mini mode opens by default** — new installs now start in the compact mini toolbar instead of the full editor (existing users keep whatever they already had). Change it any time in Settings → Startup view
- **Reset to defaults button** — Settings has a "Reset to defaults" button (with a confirmation) that puts every preference back to how it shipped. Your saved macros and your ability to unlock your own encrypted folders are left untouched

---

## v15.58

- **No more window flicker in the background** — while sitting idle in the background (always-on-top off), Macro Studio kept refreshing its own title bar twice a second forever, which could make it flicker or briefly surface. It now goes quiet when nothing is recording or playing, so it stays put in the background
- **No more window flash over the game** — with always-on-top off, Macro Studio could briefly pop over the game when it reappeared after playback (it never stole focus, but Windows still surfaced it). It now reappears at the very back, behind everything, until you switch to it yourself

---

## v15.57

- **Custom hotkeys survive mini recordings now** — starting a recording in mini silently reverted a custom hotkey (like O) back to F8, which also made the hotkey press get recorded. The saved-settings loader only accepted the old preset keys and threw custom ones away; it now accepts any key or combo

- **Long recordings no longer get laggy** — recording used to slow down more and more the longer it ran (very noticeable past a minute of constant movement). Three causes fixed: an undo snapshot of the entire macro was being taken on every single recorded action, the crash-recovery autosave kept re-saving the growing macro mid-recording, and the window-switch detector was querying Windows on every mouse movement. Recording now stays smooth no matter how long the macro gets — and pressing Undo after a recording removes the whole session in one step

---

## v15.56

- **Hotkeys stay in sync everywhere** — changing the play/record hotkey in mini, the full window, or Settings now updates all of them together and is remembered. This also fixes the hotkey still being recorded as a key press when recording from mini with a custom hotkey

---

## v15.55

- **Action Reference brought up to date** — the in-app Help now covers Read text (OCR), Play another macro, the Jump limit, the new Wait modes (until clock time / random range), and the Discord message screenshot option

- **Encrypted folders are properly sealed now** — closed several ways a shared macro's password-protected actions could be viewed without the password (combining them into a loadout, copy/paste tricks, the raw editor, and Discord action listings). Locked content now stays hidden everywhere until it's unlocked with the password

- **Hotkeys never get recorded as actions** — pressing the play or record hotkey while recording (e.g. a custom letter key like O) acts purely as the hotkey now instead of also landing in the macro as a key press
- **Macros can't trigger their own hotkeys** — if a macro types the same letter you use as a hotkey, playback no longer stops itself: only real keyboard presses count as hotkeys now

---

## v15.54

- **Custom play/record hotkey** — the hotkey dropdowns (full window and mini menu) now have a "custom…" option: click it, press any key or combo, and that becomes your hotkey
- **Pasting out of a folder no longer drags the folder along** — copied actions used to keep their folder, so pasting them elsewhere re-created the folder around them, and renaming/unfoldering that copy secretly changed the original. Pasted actions now join the folder of wherever you paste them (or none)
- **Added actions land inside the folder** — adding an action while one inside a folder is selected now inserts it right after the selection, in the same folder — no more add-then-drag-into-the-folder every time

---

## v15.53

- **OCR dialog is compact now** — removed all the explanation paragraphs from the Read text (OCR) editor, leaving just the controls

---

## v15.52

- **Updating no longer opens a second window** — the update screen is now part of the app window itself instead of a separate floating window, so there's one window, one taskbar icon, and minimizing works exactly like normal while the update installs
- **Read text (OCR) dialog uses proper go-to dropdowns** — "If the text matches / does not match" uses the familiar next / end / specific dropdowns with a step field instead of typing the target by hand

---

## v15.51

- **Read text (OCR) action** — a new Detect action that reads the text in any screen region using Windows' built-in OCR and jumps based on what it says: check if it contains a word, equals something, or compare numbers (great for counters, wave numbers, and timers). Includes a region picker and a "Test read now" button
- **Jump actions can have a limit** — give a Jump a limit (e.g. 10) and it only jumps that many times per run, then falls through to the next step. This finally makes "repeat this section 10 times, then move on" possible without duplicating steps
- **Wait until a clock time & random waits** — the Wait action now has three modes: fixed time (as before), "until clock time" (e.g. wait until 18:00 — perfect for daily resets), and "random range" (waits a different random amount each run)

---

## v15.50

- **Undo is much more reliable now** — Ctrl+Z/the Undo button now snapshots real action changes before they happen, covering normal edits, raw parameter edits, deletes, inline delay/duration edits, drag/drop reorders, folder moves/renames/grouping, inserted actions, and newly recorded actions.
- **Discord can list one path's actions now** — the Discord bot supports `actions path <number>` so you can inspect only Main/Path 2/Path 3/etc. instead of getting the whole macro action map, and the command is included in help.
- **The update progress window can be minimized now** — the updater screen stays topmost and cannot be closed during an update, but it now uses a normal Windows titlebar so it can be minimized instead of acting like a trapped borderless overlay.

---

## v15.49

- **Cleaner UI focus and selection behavior** — removed the extra Settings header hint, reduced the dotted focus outlines on tabs/buttons/checks, fixed the Play Another Macro dialog's cramped Times row, and made action multi-select behave normally: Ctrl-click toggles rows, while a normal click selects the clicked action instead of randomly deselecting it.

---

## v15.48

- **Settings are easier to understand now** — the Settings window is grouped into clear tabs for Macro, General, Recording, Sound, and Discord instead of one long hard-to-scan page, while keeping the same saved preferences and hotkeys.
- **New macro chaining action is ready** — the Paths menu now includes **Play another macro**, letting one macro run another saved macro's Main path inline, repeat it a chosen number of times, then either continue or stop everything.

---

## v15.47

- **Cleanup** — the movement-plays-twice fix is finalized and the temporary troubleshooting log it wrote has been removed; nothing else changes

---

## v15.46

- **Fixed movement-only macros playing twice** — a mouse-movement recording could capture the same motion twice, so playback traced the whole path over again and took double the time. Recordings now capture each movement once, so they play back at the correct length

---

## v15.45

- **Recording diagnostics** — added quiet internal logging to trace why movement-only recordings could replay their motion twice; no change to how macros record or run

---

## v15.44

- **Drawings are much more see-through** — the marks are now far more transparent so the game stays clearly visible underneath, while still passing every click straight through

---

## v15.43

- **Drawings are now see-through** — marks stay slightly transparent so you can see the game underneath them, while still passing all your clicks straight through to the game

---

## v15.42

- **Playback diagnostics** — added quiet internal logging around Play so the rare "macro runs twice" report can be traced to its exact source; no change to how macros run

---

## v15.41

- **The window no longer disappears on Play when "Hide during playback" is off** — starting a macro was sometimes hiding the full window even with that option unticked; it now stays visible as it should
- **"Hide during playback" is shared between mini and full** — ticking it in one now ticks it in the other, so the setting can't get out of sync between the two views
- **Drawings no longer block your clicks** — marks used to be solid, so clicking on one didn't reach the game and could mess up a recording. The whole drawing layer is now fully click-through (empty *and* painted areas), so clicks always go to the game
- **Drawing overlay is always see-through** — no more dim tint while in Draw mode; the marks stay crisp and the screen stays clear in both Draw and Click
- **Fixed macro playing twice** — a short macro could start a second time right after finishing (e.g. from a doubled hotkey). A brief guard now prevents the accidental second start

---

## v15.40

- **Tap Ctrl to switch Draw / Click** — while the Draw Menu is open, press Ctrl to flip between drawing and clicking through to the game. It works even when the game has focus, so you never have to hunt for the toolbar button
- **You can leave Draw mode again** — after drawing, the overlay jumped above the Draw Menu and covered the Draw/Click toggle, so you were stuck in Draw mode. The toolbar now stays on top after each stroke, so you can toggle back to Click (or close) any time

---

## v15.39

- **Draw Menu no longer locks you out** — opening Ctrl+G could trap all input (you couldn't click anything, not even the Draw Menu). It now opens in **Click** mode where clicks pass straight through to the game at the OS level, so it can't trap you. Flip the **Draw / Click** toggle to paint (Freehand / Line / Dot, size, color); flip it back to click the game with your focus staying there

---

## v15.38

- (superseded by v15.39 — the Draw Menu rework in 15.38 still trapped input on some setups)

---

## v15.37

- **Draw Menu input rebuilt for reliability** — drawing now polls the real Windows Ctrl key, left mouse button and cursor position directly, so normal clicks pass through while `Ctrl + left-click drag` draws on the overlay

---

## v15.36

- **Draw Menu Ctrl detection fixed** — drawing now checks the real Windows Ctrl key state, so `Ctrl + left-click` still works even right after opening the Draw Menu with `Ctrl+G`

---

## v15.35

- **Draw Menu controls corrected** — drawing now requires holding `Ctrl` and left-clicking/dragging, so normal clicks are not trapped by the draw overlay
- **Draw Menu hotkey is global** — `Ctrl+G` now opens/closes the Draw Menu even when Macro Studio is not focused

---

## v15.34

- **Draw Menu mouse capture improved** — initial direct mouse capture was added for the Draw Menu; v15.35 corrects the controls so drawing only happens with Ctrl + left-click

---

## v15.33

- **Update available dot** — when Macro Studio knows a newer version exists, Help now shows a small red dot and the Help menu marks `Check for Updates` with a red dot too, even after you choose “Not now”
- **Update dot clears automatically** — if a later check says you are already up to date, or the app version catches up to the remembered update, the red dot disappears

---

## v15.32

- **New Draw Menu for temporary screen marks** — press `Ctrl+G` to open a small always-on-top Draw Menu and mark the screen with Freehand, Line or Dot drawing while using Mini mode or recording
- **Drawing does not get recorded** — if recording is active, Macro Studio pauses recording while the Draw Menu is open and resumes afterward, so the marker clicks/lines do not become macro actions

---

## v15.31

- **Discord bot replies look much cleaner now (experimental)** — the control bot now uses a shared polished embed style with consistent colors, footer, timestamps and safer trimming, plus cleaner action/settings/live-position cards
- **Discord commands now have focused help** — commands such as `settings help`, `action help`, `loadout help`, `speed help` and `autoshot help` now show specific command instructions instead of only the big general help card
- **`action` and `actions` are clearer** — `action` now opens the action command guide, while `actions` is the one that lists your macro steps, so the two commands no longer feel mixed up

---

## v15.30

- **Mini timer is visible again** — while recording or playing in Mini mode, the elapsed timer now appears at the start of the Mini window title (for example `00:12 - Macro Studio Mini`) so the smaller toolbar no longer cuts it off, while the Rec/Play buttons stay clean

---

## v15.29

- **Cleaner, smaller Mini window** — the mini toolbar now uses real icons (bigger icon, smaller caption) like a proper toolbar, the buttons fill the whole window with no dead space below, and the window itself is more compact
- **Update screen can't be bypassed anymore** — while an update is downloading, the "Updating…" cover now always stays on top, blocks clicks, and follows the window when you move it. Before, moving the window (mini or full) could expose the app and let you interact mid-update

---

## v15.28

- **Even more Discord control (experimental)** — `info` (quick macro summary), `paths` (each path's steps, loop count and live position), and `loopdelay <ms>`. You can now also build macros remotely: `action add <type> …` (delay/key/text/click/comment/link/stop), and per-step `move <pos>`, `dup`, and jump `target` editing

---

## v15.27

- **Edit actions from Discord + cleaner bot UI (experimental)** — `action <step>` now lets you change a step live: `delay`, `key`, `text`, `x`/`y`, `button`, `clicks`, jump `target`, loadout `set`, or `delete`. The `actions` list is grouped by path with folders shown and their actions indented, and the bot's help/replies were restyled to match Macro Studio

---

## v15.26

- **More Discord control (experimental)** — new `restart` command, plus `actions` / `action <step>` to browse steps and `loadout <step> <group>` to switch loadout scenarios remotely
- **Mini "start new macro when recording" now really starts fresh** — it was recording into the previously-selected path instead of a clean new macro. Recording in mini with that option on now properly begins a brand-new macro on the Main path
- **Uncombine a loadout** — right-click a Loadout action and choose "Uncombine" to split it back into its folders (each group becomes a folder again with its actions)
- **Detect window can now target the actual app, not just the title** — "Detect window" has a new "Match by" option: match the window title, or the app's program name. Pick "App (.exe name)" with "Roblox" to detect the real Roblox client (RobloxPlayerBeta.exe) and ignore browser tabs that just have "Roblox" in their title

---

## v15.25

- **Anchor preview really stays out of captures now** — the previous attempt still caught the box because the screen hadn't repainted yet. It now waits for the box to fully disappear before capturing an image/pixel or running "Test detection"

---

## v15.24

- **The Windows key now works** — a Key Press (or hotkey) using the Windows key did nothing because it wasn't recognised. "win" / "windows" / "super" (and the right-Win and menu keys) are now sent properly
- **New "Detect window" action** — checks which app/window is focused and branches on it, just like image detection. For example, after opening a Roblox link you can check "is Roblox focused?" — if yes continue, if no jump to a Change Window step. Includes a "Use current window" button to grab the title automatically
- **Tidier action menu** — actions were piling into "Misc" and getting hard to find. Window Change, Restore Window and Open Link now live in a new "Window" group, and "Detect window" sits under "Detect", so things are easier to locate
- **Action Reference brought up to date** — it now documents Detect Window, Open Link, Loadout, and the new "lock to this action" option, with a matching "Window" tab
- **Anchor preview no longer gets captured** — the on-screen anchor search box now disappears right before you capture an image/pixel or run "Test detection", so it won't accidentally end up in your captured image
- **Faster stop** — stopping a macro (especially with several paths) no longer freezes for a few seconds; it now releases quickly so a second tap won't accidentally restart playback

---

## v15.23

- **Combine into loadout now works with folders** — selecting whole folders (even collapsed) and choosing "Combine selected → loadout" now correctly pulls in all their actions, instead of doing nothing

---

## v15.22

- **No more silently losing a macro when recording in mini** — with "Start new macro when recording" on, beginning a recording in mini used to wipe your current macro with no warning. It now asks to save first if you have unsaved changes (so the "did you want to save?" prompt actually appears)

---

## v15.21

- **New Loadout action (combine groups into one)** — select some folders (and/or actions), then ⋯ Misc → "Combine selected → loadout" to merge them into a single Loadout step. Double-click it to choose which group is active; only the active group plays. Great for keeping several setups ready for different scenarios and switching between them in one click

---

## v15.20

- **Much less lag while recording** — recording lots of clicks and movements no longer slows the app to a crawl. Each new action is now added to the list instantly instead of rebuilding the whole list every time; the full refresh happens once when you stop recording

---

## v15.19

- **Image Detect lock checkbox now shows properly** — the "Lock to this action" tick was getting clipped off the edge; it's now visible and tickable
- **"(locked)" shown in the step list** — Jump and Image Detect steps now show a "(locked)" tag in their value (next to "(dominant)") when their target is locked, so you can tell at a glance

---

## v15.18

- **Folders really stay open now** — the previous fix didn't fully take; folders could still snap shut (or pop a different one open) when you edited inside them. The open/closed state is now read at the right moment, so folders behave
- **Lockable target for Image Detect** — when an Image Detect "Go to" is set to a specific step, you now get the same "Lock to this action" tick as Jump, so the target follows that action when you reorder or insert steps
- **Image Detect shows the chosen step correctly** — a saved "specific" Go-to used to display as a raw number in the dropdown with no step box; it now correctly shows as "specific" with the target step filled in and editable

---

## v15.17

- **Folders stay open while you work in them** — opening a folder and then editing or adding an action inside no longer snaps it shut (and no longer randomly pops a different folder open). Folder open/closed state is now remembered correctly
- **New "Open link / URL" action** — add a step that opens any link in your default browser: a website, a search link, or a Roblox private-server / share link. Find it under the "⋯ Misc" actions

---

## v15.16

- **Lockable jump targets** — when editing a Jump you can now tick "Lock to this action". The jump remembers the actual step you picked, so if you add, remove, or reorder steps, the jump number auto-adjusts to keep pointing at that same action instead of going stale
- **Ctrl+W closes the current path** — a quick shortcut to delete the path you're viewing (with the same confirmation as the × button). It does nothing on the Main path, which can't be closed

---

## v15.15

- **Anchor search-area preview** — when you select an Image Detect action set to "search relative to anchor", a box now appears on screen showing exactly where it will look (based on the last anchor it found). The box stays put even after the macro stops, and you can still click through it
- **Path tabs now really fit the window** — the previous attempt wasn't shrinking enough and tabs still ran off the edge. They now scale down properly (smaller text, shorter labels, and on a very tight fit the loop box shows only on the active path) so every path is always visible
- **Image Detect "Target step" sits in the right place** — when a "Go to" is set to a specific step, the target-step box now appears directly under it instead of below the "Limit tries" section

---

## v15.14

- **Anchor settings no longer get wiped when editing** — editing an Image Detect action in the detailed editor used to silently erase its advanced options (anchor, click-on-found, retries). Those settings are now kept when you save
- **Path numbers stay correct after editing** — changing a step's delay/timing in a parallel path no longer resets its numbers from "5.1, 5.2…" back to "1, 2…"
- **Warning before deleting a path with actions** — clicking a path's × when it still has steps in it now asks first, with a "Don't show this again" option
- **Path tabs always fit the window** — when you have many paths or a smaller window, the path tabs now shrink so every path stays visible instead of running off the edge
- **Discord bot help is clearer (experimental)** — command examples now show `<step>` / `<number>` placeholders instead of fixed sample values, and the "experimental" tag sits next to the bot's name
- **Discord status shows more (experimental)** — `status` now also tells you when auto-announce or auto-screenshot is on, including how often screenshots are taken
- **Discord auto-screenshot accepts time units (experimental)** — set the interval as `30s`, `5m`, `4h`, etc., not just a number of seconds

---

## v15.13

- **Fixed scrolling in Settings** — in the Preferences tab the mouse wheel used to stop part way down, making the lower options (including the Discord bot section) hard to reach. The wheel now scrolls the whole tab all the way to the bottom

---

## v15.12

- **Fixed image macros breaking after repeated sharing** — each time an image-based macro was exported and re-imported, the saved picture's filename kept getting longer, and after enough rounds it could grow past Windows' filename-length limit and stop working. Imported images now get a short, fresh name every time, so they keep working no matter how often a macro is shared back and forth
- **Set Macro Studio up like a real installed app** — the first time you open it (and once for existing users after this update), it offers to move itself into a permanent spot in your Windows user folder, so future updates and all your files stay in one place no matter where you originally extracted it. After that it can add Start menu and desktop shortcuts for you, and shows you how to pin it to the taskbar
- **Your settings now survive re-downloading or reinstalling** — preferences, hotkeys, and your Discord bot setup used to be stored next to the app, so re-downloading the ZIP or extracting it somewhere new could wipe them. They're now kept in your Windows user folder instead, so updating, re-extracting, or moving the app no longer loses your settings. Your existing settings are moved over automatically the first time you run this version

---

## v15.11

- **Rename saved macros from the Files panel** — right-click any macro in the Files sidebar and choose Rename to give it a new name right there, without opening the folder in Explorer

---

## v15.10

- **Discord bot commands no longer need a space after the prefix (experimental)** — you can now type the command right after your prefix, so `!help` works just as well as `! help` (and `!ms play` or `!msplay` both work). Both styles are accepted

---

## v15.09

- **Fewer false antivirus warnings** — the program file now carries proper version and publisher details (you'll see them in the file's Properties), and a compression step that some antivirus engines mistook for something suspicious has been removed. The result is fewer false flags from scanners — at the cost of a slightly larger download

---

## v15.08

- **The Discord bot's messages now look like clean cards (experimental)** — the bot's replies (help, status, where, settings, screenshots and the rest) are now proper color-coded Discord embeds with titled sections instead of plain text, so they're far nicer to look at and much easier to scan for the command you want

---

## v15.07

- **A lot more Discord bot commands (experimental)** — the Discord control bot can now do much more from chat: change playback `speed` and `loop` count, `jump` / `playfrom` to a step, see exactly `where` each path is right now, take a `shot` (screenshot) or have it auto-send screenshots on a timer with `autoshot` (without interrupting your macro), `list` and `load` your saved macros, and change app `settings`. The command prefix is now fully changeable (no longer stuck on `!ms`), `help` explains every command, and it can announce in your channel when a macro finishes
- **What's New now shows everything you missed when updating from an older version** — if you hadn't updated in a while, the What's New card only showed the newest version's notes; now it shows a scrollable history of recent releases so you can catch up on everything that changed since you were last up to date

---

## v15.06

- **New (experimental): control your macro from Discord** — you can now connect your own Discord bot and run your macro with simple chat commands: `!ms play`, `!ms stop`, `!ms pause`, `!ms resume`, `!ms jump 1.1`, and `!ms status`. It's off by default, set up entirely in Settings → Discord bot (experimental), and only your own Discord account can command it — so it's private to you. Each person uses their own bot, so it only ever controls their own macro
- **No more lag when deleting or rearranging lots of actions** — large macros (especially ones with image-detection steps) used to freeze for a while when you deleted or moved many actions at once; the action list now reuses image previews instead of rebuilding every one from scratch each time, so it stays snappy
- **Path step numbers always match the open path** — fixed a glitch where a path tab could look selected while the list showed another path's numbering (e.g. Path 5 highlighted but steps shown as 1, 2, 3); the highlighted tab now always matches what's actually on screen

---

## v15.05

- **Discord messages can now include a screenshot** — the Send Discord message action has a new "Also send a screenshot" tick. Turn it on and your message arrives with a picture attached: pick a specific area of the screen with "Select region", or leave it on "Full screen" to send the whole thing. Handy for getting a snapshot of exactly what was on screen when the macro reached that point

---

## v15.04

- **Trusted friends can unlock protected folders with your password** — locking a folder now asks you to create and confirm a password; your own installation can still unlock it directly, while someone you shared the macro with can use “Unlock with password” to reveal and edit the actions when you choose to trust them
- **New Discord webhook message action** — Misc now includes “Send Discord message”, where you can paste a Discord webhook link and write a multiline message that is sent when playback reaches the action; the private link stays out of the action list, failures are clearly reported, and putting the action in a protected folder encrypts it when sharing
- **Instant Type Text no longer overwhelms apps and drops characters** — interval 0 now types through tiny, extremely fast native batches instead of one oversized burst, resumes safely from only the unsent part if Windows rejects a batch, never touches the clipboard, and prevents parallel paths from mixing two messages together

---

## v15.03

- **New: lock a folder so others can run it but can't see, edit, or copy it** — you can now lock a folder of steps. Share the macro and the other person can still play it normally, but they can't open the folder, view the steps inside, edit them, copy them, or unlock it — only the computer that locked it can unlock it again. Perfect for sharing a macro without giving away how it works
- **One-time safety check before running a locked macro from someone else** — the first time you play a locked macro that another person made, Macro Studio shows a quick "Trust & Run" confirmation so you know it contains hidden steps before anything runs; once you've trusted that macro it won't ask again

---

## v15.02

- **Folders and their actions now drag exactly where intended** — drag a folder header to move its complete block, place actions at an exact position inside an open folder, append beneath its final child, or follow the full-width indicator to place them outside; right-click also provides Move folder up/down
- **Folders now stay neatly collapsed by default** — fresh folders begin closed and no longer reopen themselves after grouping, dropping, selecting, refreshing or playback highlighting, while a folder you manually open stays open during the current session

---

## v15.01

- **The compact detector has a little more breathing room** — Image / Color Detect is now 500px wide so capture buttons and timing labels remain fully readable without returning to the oversized layout

---

## v15.00

- **Open dropdowns no longer float over settings while scrolling** — scrolling with a list open now closes it first, keeps the selected value unchanged and then moves the page normally
- **Zero-interval Type Text is genuinely instant without using the clipboard** — setting Interval to 0 sends the complete message in one batched Windows input operation, while positive intervals still type character by character; the editor and Action Reference now explain both modes clearly
- **Image / Color Detect is dramatically narrower** — the two-column editor is reduced from 760px to 480px with short non-stretching fields and compact optional controls, without removing detection features or causing horizontal clipping

---

## v14.99

- **Scrolling no longer changes form controls by accident** — using the mouse wheel in Preferences or an action editor now scrolls the page without cycling a focused or open dropdown to another value
- **Checkboxes are clean and readable again** — action options now show one clear checkbox indicator without the green block and duplicate tick obscuring its state

---

## v14.98

- **What's New now shows every update you missed** — updating across several versions displays each changelog section together with clear version headings, so moving from v14.94 to v14.98 shows v14.95, v14.96, v14.97 and v14.98 instead of only the newest entry; one obvious Close all button dismisses the complete list
- **Key Press is separate from detection again** — Image / Color Detect now focuses only on detecting and branching; add the normal Key Press action afterward when needed, avoiding duplicate and confusing key controls inside detection
- **Image / Color Detect is even narrower** — the compact split editor is reduced to 760px wide with a smaller preview and tighter controls while keeping its important options visible

---

## v14.97

- **Image / Color Detect is now genuinely compact** — the split layout remains, but the window is much smaller with a shorter preview, 2×2 capture controls, tighter spacing, shorter labels and no redundant tutorial text; all important options fit without the oversized window or long scroll

---

## v14.96

- **Image and colour detection are now one clear action** — use Image / Color Detect for normal images or Capture pixel for colours; captured pixels automatically use the fast colour scanner in a defined Region, and the separate Color Detect option has been removed from the add menu
- **Detection can press a key immediately and rearm cleanly** — choose a key inside the same detection action and optionally wait for the image/colour to leave before detecting the next one, so timing-sensitive macros no longer need a separate Key Press step
- **Detection speed is controlled per action** — the duplicate global speed preference has been removed; every new detection starts at 250 ms and can be changed directly in that action without another setting silently overriding it
- **Image / Color Detect now fits in a two-column editor** — search and matching controls sit beside found/not-found behavior, keeping the important options visible without a long scroll

---

## v14.95

- **Action Reference now has clickable action groups and global search** — switch directly between Mouse, Text/Key, Wait, Detect, Misc and Paths instead of scanning one long page; searching still checks every group so the active tab never hides the action you need

---

## v14.94

- **Action Reference is now searchable, colour-coded and up to date** — actions are grouped clearly, important options stand out, and the guide now covers current features such as raw mouse movement, capture offset, dominant jumps, colour regions, folders and per-path loop settings
- **A What's New card now appears after updates** — each new version shows a short explanation of what changed, with a “Don't show this again” option; it can also be opened anytime from Help
- **GitHub and in-app update notes now match** — both use the same concise explanations from the changelog, without developer-only coding details

---

## v14.93

- **Fixed the taskbar showing a generic/folder icon instead of the app icon** — a pinned Macro Studio taskbar shortcut could end up with an empty icon source, so Windows drew a plain folder/blank icon rather than the Macro Studio logo (especially noticeable while the app was open). The app now repairs pinned shortcuts to take their icon straight from the program file itself, which always carries the correct icon, and applies the repair once automatically on the next launch

---

## v14.92

- **Fixed the app showing up twice in the taskbar** — the taskbar-icon change in v14.91 gave the running window a separate Windows identity from its pinned shortcut, so the pin and the open app appeared as two separate taskbar buttons instead of one. That change has been reverted, so the pinned shortcut and the running app share a single taskbar button again

---

## v14.91

- **The taskbar now reliably shows the Macro Studio icon** — the running app could appear in the taskbar with a generic or wrong icon (for example a plain Python or folder icon) instead of the Macro Studio logo, and taskbar pins couldn't always find the right artwork. The app now registers its own Windows app identity at startup, so Windows consistently uses the Macro Studio icon for the taskbar button and for pinning — for everyone, not just on one machine

---

## v14.90

- **Existing pinned taskbar shortcuts now repair their icon automatically** — after an update, a Windows `.lnk` could keep its own old PyInstaller artwork even when Explorer correctly showed Macro Studio’s new logo. On startup Macro Studio now detects taskbar shortcuts that target that exact installed EXE, assigns the bundled icon explicitly, and asks Windows to repaint it. Unrelated pins are never changed, and newly created pins are detected on the next launch

---

## v14.89

- **Windows now refreshes Macro Studio’s EXE icon automatically after an update** — portable in-place updates could leave Explorer, Properties, the taskbar, or Task Manager displaying an older cached PyInstaller icon even though the new executable contained the correct logo. Macro Studio now fingerprints each changed build and safely notifies Windows Shell to refresh that executable’s icon once, without deleting icon databases or restarting Explorer

---

## v14.88

- **Pinned and running Macro Studio windows group together again** — v14.87’s process-only Windows identity could make the portable EXE’s pinned shortcut and live window appear as two different taskbar icons, while Task Manager showed a generic parent row. Macro Studio now uses portable-compatible path grouping while keeping the new embedded EXE icon and native title/taskbar icon handles

---

## v14.87

- **The new Macro Studio icon now takes over the running taskbar window reliably** — Macro Studio declares its own stable Windows app identity and sends the new small/large icon directly to the native window, preventing the running app from inheriting PyInstaller’s old folder/monitor icon or stale taskbar grouping. Existing pinned shortcuts may need to be unpinned and pinned once after installing because Windows stores their old artwork separately

---

## v14.86

- **Macro Studio now has its own memorable app icon** — the new cyan macro-knot and orange recording-dot symbol is embedded into the Windows executable and used throughout full mode, mini mode, and dialogs. Explorer, Task Manager, the taskbar, and title bars now identify Macro Studio instead of showing a blank or generic file icon
- **Saved macro files can be refreshed instantly** — a small refresh button beside `SAVED MACROS` rescans `.macstudio` and `.mac` files without restarting the app or reopening the Files sidebar, while preserving the selected file and list position

---

## v14.85

- **Solid-color and pixel Image Detect results are now accurate** — OpenCV could report a completely unrelated solid-color image as a perfect 100% match. Solid templates now use a matcher designed for them, while a captured pixel searches for the closest real pixel and only reports 100% for an exact color
- **Color Detect can now power fast rhythm-game controls** — define a tiny detection region, keep watching with no timeout, and immediately press a chosen key when the target color enters it. The action can wait for that color to leave before rearming, preventing one note from triggering repeatedly, and its action row clearly shows the region, color, tolerance, and key
- **Detection intervals now go as low as 10 ms** — Preferences and individual Color Detect actions support rapid checks for tiny regions. Small color scanners stay warm between notes and refresh safely in the background, giving fast reactions without repeatedly capturing the entire screen or paying capture startup cost

---

## v14.84

- **The whole interface now scales to your screen instead of shrinking** — on high-resolution screens the app used to render at one fixed size, which looked tiny on a 1440p or 4K display. The entire UI — both full and mini mode, toolbar rows, text, table columns and rows, thumbnails, sidebar, debugger, and all the action/settings dialogs — now grows together proportionally to your resolution (about 1× at 1080p, 1.33× at 1440p, and 2× at 4K), so it stays readable and correctly laid out on any screen. Your macro click, recording, and image-detection coordinates stay physical and unchanged

---

## v14.83

- **Full interface stays visible on high-resolution displays** — Windows display scaling could enlarge classic interface text and icons without enlarging their rows, causing toolbar labels such as Mouse, Text/Key, Wait, Detect, Misc, and Paths to disappear or become clipped. The interface now keeps every control in one consistent size system while preserving accurate mouse, image-detection, and recording coordinates

---

## v14.82

- **UI looks consistent on every screen resolution** — on higher-resolution or scaled displays the interface used to look stretched or misaligned (parts of it enlarged while others didn't), because the app was auto-scaling only some of its controls. The whole interface now renders at a single consistent size on every screen, so it looks the same no matter the resolution
- **Debugger no longer blows up the window size** — opening Debugger Mode on a high-resolution screen could suddenly make the whole window balloon to a huge size. The debugger panel now simply shares space inside the existing window, so opening it never resizes the window
- **Window comes back properly after you stop a macro** — when "Hide on play" hides the window during playback, stopping the macro now reliably brings it back: if "Always on top" is on, it pops to the front (instead of getting stuck behind a fullscreen game); if "Always on top" is off, it still reappears, just without forcing itself in front

---

## v14.81

- **Manually-added key presses now actually register** — a key-press action you added by hand often did nothing in games; it was being pressed and released too fast for the game to notice. Key presses now hold briefly (at least ~35ms) so they register reliably, and the "Hold duration" you set in the key-press editor is now saved and used (it was being ignored before)
- **Capture a relative move offset by moving the mouse** — in the Mouse Move action, when "Relative to current mouse position" is on, a new "Capture offset" button lets you just move the mouse the distance/direction you want and press Space; it fills in Offset X/Y from how far you moved (with a live readout as you go), so you don't have to guess the numbers

---

## v14.80

- **Restore/Change window keeps fullscreen** — the Restore window action (and Change window) was knocking maximized/fullscreen windows back to windowed; it now only un-minimizes a minimized window and otherwise brings the window forward in its current state, so fullscreen stays fullscreen
- **Speed shown on the playback hint overlay** — when playback speed isn't 1×, the speed now appears right next to the Play/Stop & Record hotkey hints on the floating overlay (top-center of the screen during playback), so it's visible at any resolution; the whole overlay is also more subtle now (more transparent, quieter colors, no loud border)

---

## v14.79

- **Speed badge so high playback speed can't trick you** — a bright ⚡ badge now appears in the top bar whenever playback speed isn't 1×. High speeds shrink every delay/timer (e.g. at 100× a 1-second wait becomes 10ms), which can look like "delays are being skipped"; the badge makes it obvious when speed is the cause
- **Clearer checkbox ticks** — checkboxes in the action editors now show a clear ✓ and accent-bold label when ticked (the previous styling rendered oddly on some setups)
- **Debugger: hide during playback when not stepping** — Debugger Mode now lets "Hide during playback" work as normal; it only forces the window to stay visible when Step mode is on (since you need to click Next step), with a clear note explaining why
- **Debugger: clearer detection log** — each image check now logs which step it was, leads with ✓ FOUND / ✗ not found, and adds a hint when a miss is "so close" (lower the Match %) or "way off" (wrong image/area)

---

## v14.78

- **Checkboxes show their ticked state clearly** — checked boxes in the action editors (like "Dominant", "Relative", etc.) were almost invisible on the dark theme; a ticked box now fills with the accent color and its label turns accent-colored and bold, so you can tell at a glance what's on

---

## v14.77

- **Path tabs stay put (really fixed this time)** — the Main/Path 2/Path 3 tabs were disappearing (and in some cases never showing at all). The tab row is now locked in its position and only its contents are rebuilt, so the tabs always stay visible — including when you open Debugger Mode

---

## v14.76

- **New: Dominant jumps** — Jump and Path Jump actions now have a "Dominant" checkbox. A normal jump to another path waits for that path to finish its current step (so its delays/timers are respected). A **dominant** jump force-interrupts the target path's current delay or image-wait *immediately* and sends it to the step you chose — use it when you need a path yanked out of whatever it's doing right now. Dominant jumps show "(dominant)" in the step list

---

## v14.75

- **"Park until jumped" now works** — a path sitting on a very long (or "inf") delay can now be woken up by a jump from another path; previously a long delay blocked the path completely so jumping to it did nothing; a normal, finite delay still runs its full time exactly as set (only Stop cancels it). In short: a finite timer waits that long; an infinite delay parks the path until a jump or Stop releases it

---

## v14.74

- **Jumps and delays are now reliable in parallel-path macros** — an action's own "go to" (including image/color detection branching) used to share the same internal channel as cross-path jump signals, so heavy parallel-path jumping could override a step's own jump or make delays behave unpredictably; an action's own jump now always applies directly and can never be overridden by other paths; cross-path jumps still work and are applied cleanly between steps; delays always run their full time
- **Path tabs no longer disappear when opening Debugger Mode** — the Main/Path 2/Path 3 tabs could vanish (until an app restart) after the layout changed; they now always stay in their correct spot

---

## v14.73

- **Delays are no longer skipped in jump-heavy macros** — if parallel paths were sending jumps frequently, an action's delay (and Wait/delay steps) could get cut short because an incoming jump interrupted the wait; delays now always run their full time and the jump is applied right after, so your timing is honored; image-detection waits still respond to jumps instantly as before

---

## v14.72

- **Hotkeys are disabled during an update** — pressing the Play or Record hotkey while an update was downloading/installing could start a macro mid-update and break things; now the hotkeys (and the Play/Record buttons) are locked out for the whole update and restored automatically if the update is cancelled or fails

---

## v14.71

- **Raw recording now handles hold-and-move camera control** — when raw movement recording is on and you hold a mouse button (e.g. right-click) while moving the camera, it's now recorded as press → movement → release so the button stays held during playback and the camera actually moves; a quick click with no movement is still recorded as a normal click, and a long stationary hold as a hold; if recording stops mid-hold the button is released cleanly

---

## v14.70

- **New: Raw mouse movement recording (for locked-camera games)** — added a recording mode that captures your actual physical mouse motion instead of the cursor position; this finally records camera movement in games that hide/lock the cursor, like holding right-click in Roblox, where the pointer doesn't move but the camera does; switch it on in Settings → Recording → "Mouse movement capture" → Raw movement (the default stays Cursor position, which is best for normal clicking); recorded camera movement plays back as true relative motion at the original speed

---

## v14.69

- **Better drag-and-drop with folders** — dragging an action onto a folder now drops it at the **end** of the folder (it used to land at the top); reordering actions inside a folder now reliably keeps them in the folder, even when moved to the folder's first or last position; and dragging an action out of a folder removes it from the folder as expected

---

## v14.68

- **Image thumbnails show inside folders again** — image-detection steps placed inside a folder were getting their preview icon clipped by the indentation; the icon column now widens automatically when folders are present so the thumbnails stay fully visible

---

## v14.67

- **Crash recovery / autosave** — Macro Studio now automatically keeps a backup of the macro you're working on while you edit; if the app crashes or is closed unexpectedly, the next time you open it you'll be asked whether to recover your unsaved work, so you don't lose what you were building; the backup is cleared automatically when you save or close normally

---

## v14.66

- **Debugger no longer cuts off the top menu** — opening Debugger Mode now grows the window to make room for the debugger panel instead of squeezing the menu, toolbar and step list above it (which could get clipped so the Files/Path buttons disappeared); closing it shrinks the window back to its previous size

---

## v14.65

- **Debugger panel resizing actually works now** — the previous resize handle couldn't make the panel grow because the step list above refused to shrink; the debugger is now a proper split panel with a draggable divider (the orange bar between the step list and the debugger), so you can drag it to any height and the step list shrinks to make room

---

## v14.64

- **Debugger panel resize is now actually grabbable** — the resize handle was a thin, nearly invisible strip that was almost impossible to grab; it's now a clearly labeled "drag to resize" bar across the top of the debugger panel that highlights when you hover it, so you can easily drag it taller to see the full log

---

## v14.63

- **"Always on top" now works during playback** — if you have "always on top" enabled, the window now stays on top while a macro is running instead of dropping behind other windows; if it's off, it still steps aside so it can't block game clicks
- **Debugger Mode never hides during playback** — when Debugger Mode is on, "Hide during playback" is ignored so the debugger panel stays visible and you can still click "Next step" in Step mode
- **Debugger panel resizing fixed** — dragging the top edge of the debugger panel now smoothly resizes it (with a visible drag handle), so you can make it tall enough to see everything

---

## v14.62

- **Debugger Mode redesigned** — the debugger is now a full-width panel docked at the bottom (instead of a cramped side panel that squeezed the step list), so your steps and path tabs stay fully visible; you can drag its top edge to resize it; and entering Debugger Mode now recolors the whole title bar amber so it's obvious you're in a different mode
- **Debugger: cleaner detection log** — image-detection results now read simply as "detect image: 73% < 85% ✗ not found" instead of dumping the long internal file name; parallel-path actions are now logged too (labeled by path, e.g. 2.1, 2.2)
- **Debugger: clearer Step mode** — the "Next step" button is now greyed out until Step mode is actually on, so it's obvious when it does something
- **Dark scrollbars everywhere** — scrollbars across the whole app (step list, dialogs, settings, debugger, sidebar) are now dark to match the theme instead of showing as bright white Windows-style bars

---

## v14.61

- **New: Debugger Mode** — click the "HAMZA" name in the title bar to open Debugger Mode (click again to close). A side panel appears with three tools: a **live log** that shows every action, loop, jump and image-detection result with its match score as the macro runs; a **Step mode** that pauses playback before each step so you can advance one action at a time with a "Next step" button; and a **"Test selected detection"** button that runs an Image Detect step right now and pops up exactly what the macro sees versus the template image, with the match score — so you can finally see *why* a detection passes or fails instead of guessing. (Right-clicking "HAMZA" still opens the raw parameter editor as before.)

---

## v14.60

- **Custom playback speed works in Mini mode** — the "Set Custom Speed" dialog now actually appears when you open it from the Mini window (it was opening invisibly behind the hidden main window before)
- **Higher speed limit** — custom playback speed can now go all the way up to 100x instead of being quietly reset
- **Custom speed stays selected** — after setting a custom speed it now shows up as a checked option in the Speed menu (both full and Mini), and no longer vanishes when you reopen the menu or set another one
- **Hotkey reminder badge during playback** — when "Hide during playback" is on, a small badge now appears showing your Play/Stop and Record hotkeys so you always know how to stop; can be turned off in Settings → Preferences
- **Finish sound off by default** — the macro-finished sound is now off out of the box; turn it on in Settings if you want it (your choice is remembered across updates)
- **Ctrl+S to save** — you can now save the current macro with Ctrl+S

---

## v14.59

- **Folders: drag actions in and out** — drag actions onto a folder header (or between two actions inside an open folder) to move them in; drag them out anywhere else and they leave the folder automatically
- **Folders: create empty folders** — Misc → Folder with nothing selected now creates an empty folder you can drag actions into, instead of requiring a selection first
- **Folders: rename and ungroup** — right-clicking a folder header now opens a folder menu with "Edit name…" (renames the folder everywhere) and "Ungroup" (removes the folder but keeps all its actions in place)
- **Folders: clearer visuals** — actions inside a folder now have a subtly different background so it's obvious at a glance what's grouped and what isn't, even with multiple folders and loose actions mixed together

---

## v14.58

- **Smoother multi-select in the step list** — clicking an already-selected action now deselects just that one (the rest of the selection stays); double-clicking any action opens its editor even during multi-select, without destroying the selection; and right-click → Edit now edits the action under the cursor instead of the first selected one

---

## v14.57

- **Folders: group actions under named, collapsible headers** — select actions and use Misc → "Folder (group actions)" (or right-click → "Move to folder") to group them under a named folder in the step list; folders are purely visual — playback, step numbers, and jumps are completely unaffected; folder rows carry no step number, grouped actions appear indented, and clicking the arrow collapses or expands the folder; right-click also lets you move actions into an existing folder or remove them from one

---

## v14.56

- **Massive CPU reduction for image detection** — the real CPU hog has been found and fixed: in full and region_all search modes, every check was capturing every single window on the system (forcing each one, including the game, to fully re-render); now only windows that actually overlap your search area get captured, invisible ghost windows are skipped entirely, and the template image is cached instead of re-read from disk on every check; a region_all check that took ~700 ms of heavy work now takes ~150 ms, and a plain region check ~37 ms — combined with the poll interval setting this brings background CPU usage down dramatically
- **Recorded waits are no longer skipped** — when recording (especially in Mini mode), an intentional wait before your first action was being silently removed, so playback skipped it; recordings now keep every delay exactly as you performed it
- **Game CPU usage also reduced** — the old all-windows capture was forcing the game itself to render extra frames on every detection check, inflating the game's own CPU/GPU usage; with the overlap filtering this no longer happens when the game is outside your search area

---

## v14.55

- **Image detection reliability fix (second attempt)** — the previous fix still left the door open for the screen-capture call to hang indefinitely when the game renderer is under heavy load, which would silently freeze detection while the macro kept looping; the capture now uses a fresh connection on every check instead of reusing a cached one, eliminating the hang and stale-connection issues entirely; the CPU cost difference is negligible compared to the actual screen capture and image matching work

---

## v14.54

- **Image detection no longer goes blind mid-run** — after the macro had been running for a while, screen captures could silently fail and the macro would keep looping but stop detecting anything; the root cause was leaked Windows graphics handles that eventually exhausted; they are now properly released before each retry, so detection stays reliable no matter how long the macro runs

---

## v14.53

- **"End" no longer stops an infinite-loop macro** — when a macro is set to loop forever, hitting "end" (e.g. image not found → end, or a stop action) now restarts that path from step 1 instead of stopping the whole macro; this applies to the main path and all parallel paths; only pressing the Stop button or hotkey will actually stop an infinite macro

---

## v14.52

- **High poll intervals no longer cause the macro to stop early** — when using a slow poll interval (e.g. 2 s) and a cross-path jump signal arrived while image detection was sleeping, it could mistakenly trigger the "not found" handler and stop the macro; it now correctly recognises that a redirect is pending and lets the jump apply instead
- **Cross-path jump signals in parallel paths no longer get lost** — when a jump signal arrived mid-action in an extra path (Path 2, Path 3, etc.), it could be silently discarded; extra paths now have the same post-action jump check that the main path already had

---

## v14.51

- **Settings: image detection poll interval** — a new "Performance" section in Settings lets you choose how often image detection checks the screen (250 ms up to 2 s); higher values mean fewer screen captures per second and noticeably lower CPU usage, at the cost of the macro reacting a little slower when the target image appears; the setting applies globally to all image detection actions at once

---

## v14.50

- **Significantly reduced CPU usage during playback** — internal timing loops were waking up 200 times per second per path thread just to check for signals; they now wake up 40 times per second instead, cutting thread-scheduling overhead by 5× with no noticeable change in responsiveness
- **Faster screen captures during image detection** — previously a new screen-capture connection was opened and closed on every single poll (up to several times per second across parallel paths); the connection is now kept open and reused, reducing per-capture overhead significantly

---

## v14.49

- **New action: Restore window** — a new action in the Misc menu switches focus back to whichever window was active just before the last "Change window" action ran; useful when your macro switches to a game at the start and you want to return to your browser or other app automatically at the end

---

## v14.48

- **Image detect: "Move & click" now actually works** — the click-on-found feature was using an older input method that doesn't register in games; it now uses the same hardware-level input as every other click in Macro Studio, so it works correctly in Roblox and other games
- **Image detect: "Move & click" now works with defined search areas** — previously the click option was hidden whenever you switched to region or region_all search mode; it is now always visible and works with any search mode
- **Image detect: "Move & click" has new button and offset options** — you can now choose which mouse button to click (left, right, or middle) and add an X/Y pixel offset to shift the click away from the centre of the detected image

---

## v14.47

- **Cross-path jumps now interrupt the main path's action delay too** — previously, if a parallel path sent a jump signal to the main path while the main path was in the pre-action delay (the "Delay" field before each step runs), the jump would be ignored until that delay fully expired; the main path now wakes up mid-delay the moment a cross-path jump arrives, matching the behaviour already in place for image detection waits

---

## v14.46

- **Cross-path jumps now work even when the main path is waiting for an image** — if Path 2 (or any parallel path) found its image and sent a jump signal to the main path, the main path would ignore it until its own image detection timeout expired (potentially stopping the macro entirely via "end" before ever applying the jump); the main path now wakes up immediately when a cross-path jump arrives, just like parallel paths already did

---

## v14.45

- **Delay action: set wait time in hours, minutes, seconds, and milliseconds** — the delay editor now has separate fields for h / m / s / ms instead of a single milliseconds box; a live preview shows the total in milliseconds so you always know exactly how long the wait will be; existing delays load correctly with their time broken out into the right fields automatically

---

## v14.44

- **Mouse no longer twitches during clicks** — every click used to briefly nudge the mouse one pixel sideways before clicking; in games like Roblox this caused a tiny visible camera stutter on every action; the nudge has been removed so the cursor stays perfectly still while clicking
- **Jumps and stops now respond instantly inside parallel paths** — if an image detection step inside Path 2 (or Path 3, etc.) was actively waiting for an image, sending a jump signal or stopping that path would be ignored until the wait finished; it now wakes up immediately when a jump or stop arrives, just like the pre-action delay already did

---

## v14.43

- **Image detect: single-pixel colour detection no longer gives false positives** — when you capture a single pixel colour and set a search region, the detection now checks whether the overall colour of that region matches your target, rather than hunting for any individual pixel that happens to be close; this means it will only trigger when the area actually looks like that colour, not randomly fire because one stray pixel matched

---

## v14.42

- **Image detect: "Capture pixel" button** — a new button in the image detection dialog lets you click a single pixel on screen to use its exact colour as the detection target; the screen freezes so you can aim precisely, just like "Capture image"
- **Image detect: solid-colour and single-pixel templates now match correctly** — detecting a pure colour (e.g. a black icon or a single pixel) previously failed silently due to a mathematical edge case; it now falls back to a direct pixel-comparison method that works for any template regardless of how uniform it is
- **Image detect: preview fills the available space** — the captured image or pixel now scales up to fill the preview area properly instead of staying tiny in the corner; small templates are enlarged with crisp pixel scaling, large images are scaled down cleanly
- **Image detect: capture overlay instruction bar is smaller** — the instruction text at the top of the capture overlay is now smaller and less intrusive so it covers less of the screen while you aim

---

## v14.41

- **Image detect: solid-colour templates now work correctly** — using a small or single-colour image as a template (e.g. a pure black icon) could silently fail to match anything because the underlying maths produces an undefined result for zero-variance images; the engine now detects this and switches to a different matching method that handles solid colours correctly

---

## v14.40

- **Image detect: "Define search area" defaults to visible screen only** — clicking "Define search area" now sets the search mode to "region" (searches only what is currently visible on screen within your drawn area); previously it defaulted to "region_all" which also searched background windows; if you want background windows included you can still switch the Search dropdown to "region_all" manually

---

## v14.39

- **Image detect: defined search area now works correctly** — when you use "Define search area" in the image detection action, the macro now searches exactly the area you drew and nothing else; previously the region could be silently ignored on some systems (certain DPI settings, regions near the screen edge, or driver quirks), causing the macro to search the entire screen instead
- **Image detect: zero-size region no longer causes a bad capture** — if an older action was saved without a valid search area but still had a region mode selected, it would try to capture a 1×1 pixel area and never find anything; it now correctly falls back to a full-screen search instead

---

## v14.38

- **Resolution dialog clarified** — the "resolution mismatch" dialog now clearly explains what Yes and No each do: Yes scales all coordinates to your screen immediately (save afterwards to keep the result); No opens the macro exactly as recorded with no changes
- **No hidden scaling at playback** — the app no longer silently rescales coordinates in the background every time a macro plays; what you see in the step table is exactly what runs, making behaviour predictable and consistent

---

## v14.37

- **Resolution scaling no longer lost on record** — opening a macro recorded at a different resolution and then pressing the record hotkey to add new steps no longer overwrites the original recorded resolution; the auto-adjust dialog will continue to work correctly for your friends even after you've added new steps and re-saved

---

## v14.36

- **Resolution scaling no longer lost on save** — when you open a macro recorded at a different resolution and decline the auto-adjust dialog (letting the app scale it at playback time instead), saving the macro no longer overwrites the original recorded resolution; the scale factor is correctly applied every time you play, even after re-opening

---

## v14.35

- **Image detection: images saved inside the macro file** — image templates are now embedded directly in the `.macstudio` file as part of the save; when you share the file with a friend, the image travels with it and works immediately on their machine with no missing files
- **Image detection in parallel paths fixed** — image templates used in Path 2, Path 3, etc. were silently left out of the saved file; they are now included along with the main path
- **Old macros (plain JSON format) load correctly** — macros saved in the original JSON-only format no longer cause a silent load failure; they open as before, just without embedded images

---

## v14.34

- **No focus steal on record start/stop** — pressing the record hotkey to start or stop recording no longer brings the Macro Studio window to the foreground; focus stays on your game the entire time
- **No focus steal after playback ends** — when a macro finishes and the window re-appears, it shows without stealing focus so your game window stays active
- **Update dialog always fits screen** — the "Update available" dialog now measures its own content, centers on screen, clamps to 80 % of screen height, and shows a scrollbar if needed; the Update Now / Not Now buttons are always reachable regardless of display scaling or resolution

---

## v14.33

- **Image detect: Match % replaces Tolerance** — the threshold field was labelled "Tolerance" and stored a 0–1 value, meaning typing 0 caused every search to report a match regardless of what was on screen; it is now labelled "Match %" with values 1–100 (default 85), so 85 means the image must be at least 85 % similar before being considered found — higher is stricter; existing saved actions load and convert automatically
- **Image detect: anchor flow clarified** — "Set as anchor when found" has moved into the "If image has been found" section so it is obvious it only fires on a successful match; "Search relative to anchor" stays with the search settings and now has a description explaining it looks for a position saved by a previous action; the anchor offset tip now mentions negative Y means above the anchor point
- **Image detect: branch labels improved** — the "If image is not found" section now shows a one-line legend explaining what "end", "next", and "specific" each do so you no longer have to guess what "end" means (it stops the macro)
- **Image detect: search mode hint** — a small description line below the Search dropdown explains what each mode does at a glance

---

## v14.32

- **New path.step jump notation** — jump targets now use "path.step" format (e.g. 2.5 = Path 2 step 5, 4.1 = Path 4 step 1) instead of backticks; this works for any number of paths with no limit; old macros using backtick notation still load and run correctly
- **Step table shows path.step numbers** — the # column now shows 2.1, 2.2, 2.3… for Path 2 and 3.1, 3.2… for Path 3 so you can read the exact jump target directly from the table; the Main path still shows plain 1, 2, 3
- **Jump and Path Jump redesigned** — both actions now show a Path dropdown (Main, Path 2, Path 3…) and a Step number field instead of requiring you to type backtick notation; all "Go to" fields in Image Detect and Color Detect also accept path.step when "specific" is chosen
- **Image detect: region search fixed** — "Define search area" now sets the search mode to Region (all) by default, which searches both the visible screen and background windows in the defined area; previously the plain Region mode only checked what was visually on screen, so images inside a background app were never found
- **Image detect: region validation** — if you switch to a region-based search mode without having defined a search area first, a warning appears immediately; trying to save without a valid area shows a blocking error so you can't accidentally run an empty region search
- **Image detect: crash protection** — the image search engine now catches errors at every stage (template matching, background window capture, the poll loop, and the action handler itself); any internal failure is treated as "image not found" so the macro continues to its "if not found" branch rather than stopping the whole macro unexpectedly

---

## v14.31

- **New jump notation: path.step** — all jump targets now use a simple "path.step" format (e.g. 2.5 = Path 2 step 5, 3.1 = Path 3 step 1); this works for any number of paths without limit; the old backtick notation still loads correctly in existing macros
- **Step table shows path.step numbers** — the # column now displays steps as 2.1, 2.2, 2.3… for Path 2 and 3.1, 3.2… for Path 3, matching the jump notation exactly; the Main path still shows plain 1, 2, 3
- **Jump / Path Jump UI updated** — both dialogs now show the path.step format; Image Detect, Color Detect, and Random Jump "Go to" fields all accept path.step notation when "specific" is chosen
- **Image detect: region search fixed** — "Define search area" now enables Region (all) mode by default so the defined area is searched in both visible and background windows, not just the visible screen; previously using a defined region with a background app would never find the image
- **Image detect: region validation** — switching to a region-based search mode without first defining a search area now shows a warning; saving without a valid area shows a blocking error so you can't accidentally run a region search with no region

---

## v14.30

- **Image detect: region search fixed** — "Define search area" now enables Region (all) mode by default so the defined area is searched in both visible and background windows, not just the visible screen; previously using a defined region with a background app would never find the image
- **Image detect: region validation** — switching to a region-based search mode without first defining a search area now shows a warning; saving without a valid area shows a blocking error so you can't accidentally run a region search with no region
- **Jump / Path Jump: path picker** — both Jump and Path Jump actions now show a dropdown to select the target path by name (Main, Path 2, Path 3…) and a step number field; no more backtick notation needed; existing macros using backtick notation continue to work

---

## v14.29

- **Image detect: deeper crash protection** — the image search engine now catches errors at every level (template matching, background window capture, the poll loop itself, and the action handler); any internal failure is treated as "image not found" so the macro continues to its "if not found" branch rather than stopping unexpectedly; a screenshot failure on a bad anchor region no longer blocks the background window search from running

---

## v14.28

- **Hotkeys saved globally** — the Play and Record hotkeys are now saved in preferences so they stay the same every time you open the app, create a new macro, or switch between macros; previously they would reset to F6/F8 on each new session
- **Image detect: no-timeout mode** — a new "No timeout — keep searching until image is found" checkbox in the image detection dialog makes the action poll forever until the image appears; you can also just type "inf" in the After ms field for the same effect
- **Image detect: crash fix** — if the image search encountered an error (e.g. an anchor region with coordinates that went off-screen), the macro would silently stop; errors are now handled gracefully and the action continues to its "if not found" branch instead
- **Jump always targets Main path** — a plain step number (e.g. `3`) in the Jump or Path Jump action now always means step 3 of the Main path, regardless of which path runs the jump; use one backtick for Path 2 (`3\``) and two for Path 3 (`3\`\``); this lets any parallel path redirect the main path directly

---

## v14.27

- **Relative mouse move** — the Move action now has a "Relative to current mouse position" checkbox; when ticked, you type an Offset X and Offset Y instead of a destination coordinate, and the macro moves the mouse that many pixels from wherever it currently is (negative values move left/up); the start/end capture fields are hidden when this mode is active to keep the dialog clean

---

## v14.26

- **Image detection finds background apps** — "Full" search mode now detects images inside apps that are behind other windows, not just what's visually on screen; useful when your game is covered by another window while the macro runs
- **Focused window mode fixed** — the "Focused window" search mode now correctly searches only the window that is currently in the foreground, instead of behaving the same as full-screen search
- **New region (all) search mode** — a new search mode that searches a fixed screen region but checks every window including background ones; use this when you know exactly where something appears on screen but the app may be hidden behind another window when it does
- **Image detect help updated** — the Action Reference now documents all four search modes with plain-English descriptions so you know which to pick

---

## v14.25

- **Hold + drag recording fixed** — when you hold the mouse button and move around, the recording now captures your exact path so playback follows every point you drew, instead of snapping in a straight line from start to finish
- **Double-click on windowed apps fixed** — pressing and holding the mouse no longer sends two extra invisible mouse moves just before the click, which was causing some windowed apps to register a double-click and minimize or maximize unexpectedly

---

## v14.24

- **Anchor-relative image search** — Image Detect actions now have an Anchor section with two options: "Set as anchor when found" stores the position of a found image so other actions can reference it; "Search relative to anchor" makes the search region follow that stored position with configurable offset and size, rather than using a fixed screen region — useful whenever you need to find something near something else that moves each run

---

## v14.23

- **Update overlay fixes** — overlay no longer forces always-on-top when the app is not; it's no longer modal so you can minimize the app normally and the overlay minimizes with it instead of floating over everything else
- **Image detect region preview** — clicking an Image Detect action in the step table now flashes a red rectangle directly on screen over the configured search region (same style as the arrow/marker previews), replacing the old dialog-based preview button
- **Image detection in parallel paths fixed** — parallel paths running simultaneous image searches could corrupt each other's results; all screen captures now go through a single lock so each search completes cleanly
- **Fast stop on image detection** — stopping the macro mid-image-search now responds within 25 ms instead of waiting up to the full poll interval

---

## v14.22

- **Image detection false positive fix** — the full-screen image search now captures only the primary monitor instead of the entire virtual desktop; on multi-monitor setups the old code used an incorrect origin point which could cause the image to appear "found" at the wrong position or match content on a different monitor
- **Image detect region preview** — when an Image Detect action has a search region defined, a new **👁 Preview region** button lets you see exactly where on screen the region is; it takes a live screenshot and highlights the region with a red outline so you can verify it's in the right place before running the macro

---

## v14.21

- **Update overlay fixed in full mode** — the "Updating… Downloading…" overlay now correctly covers the full window when updating from full mode; previously it was snapping to the size of the hidden mini window and appearing as a small banner across the top

---

## v14.20

- **Resolution scaling fixed** — when opening a macro on a different screen resolution, all coordinates are now correctly adjusted; previously mouse move destination coordinates (`x`/`y`) were not being scaled at all, and recorded mouse path actions were silently skipped entirely — both are now fixed

---

## v14.19

- **Image / Color Detect cross-path jump fix** — setting a "Go to" target with backtick path notation (e.g. `1``, `2``) now works correctly in Image Detect and Color Detect actions; previously the backticks were stripped and the jump fell back to step 1 of the current path

---

## v14.18

- **Undo / Redo** — press **Ctrl+Z** to undo and **Ctrl+Y** to redo any action edit (add, delete, paste, reorder, edit); two arrow buttons (↩ ↪) appear in the menu bar and are greyed out when there is nothing to undo or redo; up to 50 steps of history are kept
- **Files sidebar right-click menu** — right-clicking any macro in the Files panel shows a context menu with: Load, **Copy file** (puts the file on the clipboard so you can paste it straight into Discord, a chat, or Explorer to share with friends), Open folder, and Delete

---

## v14.17

- **Finish sound waits for all paths** — the completion sound now fires only after every parallel path has finished, not the moment the main path ends; if you stop manually no sound plays, as before
- **Smoother auto-update** — the updater no longer deletes `_internal` before copying new files (eliminating the window where the app could launch with a missing Python runtime); a short settle pause is added before the new version starts; leftover `.bak` and `update_error.txt` files are automatically removed on a successful update
- **Build/release script fixes** — the release ZIP asset name is now correctly encoded; the release notes are correctly extracted from the README even when the version heading has extra text after the version number; the GitHub release page URL opens without a garbled prefix

---

## v14.16 — First Official Release

- **Per-path loop count** — each parallel path now has its own ↺ loop field in the path tab; set a number to override the global loop count for that path only; leave it at 0 to fall back to the global setting
- **Delayed tooltips** — tooltip popups across the entire app now wait 1.8 seconds before appearing; they no longer flash up the instant you hover, which was disruptive during normal use
- **Color Detect dialog crash fix** — opening a Color Detect action to edit it no longer crashes
- **Image Detect "click on found" extended** — the "Move & click on image location" option is now available in both Full-Screen and Focused Window search modes; a new Move speed field controls how fast the mouse glides to the found image's centre before clicking
- **New actions insert after selection** — adding an action via the toolbar now inserts it immediately after the last selected row
- **Parallel paths playback fix** — extra paths were silently skipped when the internal set_extra_paths() call was out of sync with the macro being played; the player now reads paths directly from the macro object

---

## v14.15

- **Resolution mismatch handling** — when opening a macro recorded at a different screen resolution a dialog offers to automatically scale all coordinates to your current screen
- **Always stamp resolution on save** — every save now writes your current screen resolution into the macro file
- **Color Detect dialog fix** — clicking a Color Detect action to edit it now correctly opens the edit dialog
- **Files sidebar delete / overwrite fixed** — the Delete and Overwrite buttons in the Files sidebar now show a confirmation dialog and carry out the action
- **Image Detect "click on found"** — when image is found, a new "Move & click on image location" checkbox makes the macro automatically move the mouse to the found image's centre and click it

---

## v14.14

- **Drag-and-drop reorder** — drag any action row up or down to reorder; a 2 px blue drop-line shows exactly where it will land
- **Multi-select drag** — Shift/Ctrl+click to select multiple actions then drag the whole group at once
- **Color Detect action** — new action that reads the pixel colour at an X/Y coordinate and branches based on RGB tolerance
- **Comment / Label action** — insert a visual label row into the action list with no playback effect
- **Random Jump action** — jumps to a randomly chosen step from a comma-separated list of targets
- **Finish sound notification** — new Preferences option to play a sound when a macro completes; 6 built-in presets plus custom beep and WAV file
- **Path tab labels** — extra path tabs are now labelled "Main", "Path 2", "Path 3"
- **Extra paths loop independently** — each parallel path loops the same number of times as the main path but runs entirely on its own
- **Jump signal interrupts delay** — a cross-path jump signal now cancels a running pre-action delay immediately
- **Help window** — "Action Reference" and "Keyboard Shortcuts" entries added to the Help menu

---

## v14.13

- **Per-path stop on delete** — deleting a parallel path while it is running now immediately stops that path's thread
- **Recording goes to selected path** — actions recorded while a non-main path tab is active are now correctly added to that path
- **Backtick step notation** — path tabs and step numbers now show backtick suffixes so you can visually tell which path each step belongs to
- **Global stop also stops parallel paths** — pressing Stop now signals all per-path stop events so every extra path halts immediately

---

## v14.12

- **Parallel action paths** — click "+ Path" in the menu bar to add extra paths that run concurrently alongside the main macro
- **Path tabs** — switch between paths in the editor using the path tab row
- **Path Jump action** — new action type that signals a parallel path to jump to a specific step mid-execution
- **Paths saved in macro file** — extra paths are serialised into the `.macstudio` file

---

## v14.11

- **Update overlay follows mini window** — progress overlay now tracks the mini window as you move it and sizes correctly to it
- **Action dialogs no longer flicker** — edit dialogs now appear at the correct size immediately
- **Update dialog no longer freezes app** — switching from mini to full mode while an update prompt is open no longer hides the dialog and locks all input

---

## v14.10

- **Reliable in-place update** — "Update now" renames the old EXE before replacing it so Windows file locking can never block the swap

---

## v14.09

- **Auto-sizing dialogs** — all action editors and Settings now detect small screens and add a scrollbar

---

## v14.08

- **File sidebar** — toggle with "⊞ Files" in the menu bar; search, load, overwrite, or delete saved macros
- **Mini update prompt** — update notification now appears correctly when the app is in mini mode

---

## v14.07

- **Resolution scaling** — macros now store the screen resolution they were recorded on and auto-scale on playback

---

## v14.06

- **New file extension** — macros now save as `.macstudio` instead of `.mac`; old `.mac` files still open fine

---

## v14.05

- **Update protection** — window becomes fully non-interactable while downloading an update
- **Launch lock** — updater writes a lock file before replacing files; app refuses to open if lock file is present

---

## v14.04

- **Mini loop snapping** — entering mini mode snaps any custom loop count down to 1
- **Hotkey conflict popup** — selecting duplicate hotkeys shows an error dialog and reverts the change
- **BUILD RELEASE auto-version** — bat reads CURRENT_VERSION from source automatically
