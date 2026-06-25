<p align="center">
  <img src="images/macro-studio-icon.png" width="170" alt="Macro Studio icon">
</p>

<h1 align="center">Macro Studio</h1>

<p align="center">
  <strong>Windows macro automation by Hamza</strong><br>
  Built for friends who were tired of TinyTask's limitations.<br>
  Free for anyone to use.
</p>

---

## What it does

Macro Studio lets you record and replay anything you do on screen — clicks, key presses, mouse movement, image detection, color detection, multi-step branching logic, and more. It's designed to feel simple on the surface while giving you a lot of control when you need it.

Key features:
- Smart and exact recording modes (plus raw movement capture for in-game camera control)
- Parallel action paths that run at the same time
- Image detection and color detection with branching ("if found, go to step X")
- Resolution scaling — macros recorded on one screen size adjust automatically on another
- Folders to group and organize your steps
- Mini compact mode and full editor mode
- Built-in Debugger Mode to see exactly what image detection sees
- Auto-updates from GitHub — just click Update when prompted
- Undo / redo, drag-to-reorder, multi-select, copy/paste
- Crash recovery — never lose unsaved work

---

## A look inside

**The full editor** — record clicks, key presses and real mouse movement, then see and fine-tune every step. Recorded mouse paths are even drawn right on the screen, so you can see exactly what was captured and where it starts and ends.

<p align="center"><img src="images/showcase-main.png" width="760" alt="Macro Studio full editor with a recorded mouse path drawn on screen"></p>

**Mini mode** — a tiny, always-on-top toolbar that stays out of your way while you game. Record, play, save and load without the full window in the way.

<p align="center"><img src="images/showcase-mini.png" width="360" alt="Macro Studio Mini compact toolbar"></p>

**Parallel paths & your macro library** — run several action paths at the same time, and keep every macro you've made one click away in the saved list.

<p align="center"><img src="images/showcase-workspace.png" width="500" alt="Parallel paths and the saved-macros library"></p>

**Searchable Action Reference** — every action explained, grouped by type and fully searchable, with the important options highlighted so you can find what you need fast.

<p align="center"><img src="images/showcase-action-reference.png" width="620" alt="Searchable, colour-coded Action Reference"></p>

**Built-in help & update notes** — open the Action Reference, keyboard shortcuts, or a "What's New" card (shown automatically after each update) right from the Help menu.

<p align="center"><img src="images/showcase-help.png" width="340" alt="Help menu"></p>

---

## How to download & run

### 1. Download

Go to the **[Releases page](https://github.com/Hamza122nr2/macro-studio-updates/releases)** and download the latest `Macro_Studio-By_Hamza_vXX.XX_windows.zip` file (under **Assets**).

### 2. Move the ZIP where you want the app to live

Before extracting, **move the downloaded ZIP** to the folder where you want Macro Studio to stay (for example a "Macro Studio" folder in Documents). Whatever folder you extract it in is where it lives — so pick the spot now.

### 3. Make it trusted (important!)

Because the app isn't "code-signed" (a certificate that costs money every year), Windows marks files downloaded from the internet as "blocked" and may show a scary warning. **It's a false positive** — Macro Studio isn't a virus; Windows is just cautious about apps from publishers it doesn't recognize, and an unsigned app always triggers this. Unblocking the ZIP **before** extracting removes that warning completely, and you won't get an antivirus pop-up afterward.

**Right-click the ZIP file and choose `Properties`:**

![Right-click the ZIP and choose Properties](images/1-right-click-properties.png)

At the bottom of the Properties window you'll see a **Security** line that says *"This file came from another computer and might be blocked…"* with an **Unblock** checkbox — unticked by default:

![Unblock checkbox, unticked](images/2-unblock-unticked.png)

**Tick the Unblock checkbox:**

![Unblock checkbox, ticked](images/3-unblock-ticked.png)

Click **Apply**, then **OK**. The Security line disappears — that means it worked and the file is now trusted:

![After clicking Apply the Security line is gone](images/4-after-apply.png)

### 4. Extract

Now **right-click the ZIP again** and choose **`Extract All…`**:

![Right-click and choose Extract All](images/5-extract-all.png)

### 5. Run it

Open the extracted folder and run **`MacroStudio.exe`**. No install needed.

- You can now **delete the leftover `.zip` file** — you don't need it anymore.
- **Tip:** right-click `MacroStudio.exe` → **Pin to taskbar** so it's one click to open next time.

> If Windows ever still shows a blue **"Windows protected your PC"** popup, click **More info → Run anyway**. (You normally won't see this if you unblocked the ZIP first.)

---

## Default hotkeys

- **F6** — Play / Stop
- **F8** — Record / Stop recording

---

## Found a bug or have a suggestion?

Open an issue on GitHub and I'll take a look:
**https://github.com/Hamza122nr2/macro-studio-updates/issues**
