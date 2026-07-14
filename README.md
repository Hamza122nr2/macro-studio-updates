<div align="center">
  <img src="branding/macro_studio_icon_source.png" width="112" alt="Macro Studio icon">
  <h1>Macro Studio</h1>
  <p><strong>Record simple. Build advanced.</strong></p>
  <p>A powerful Windows macro recorder and visual automation studio made by Hamza.</p>

  [![Latest release](https://img.shields.io/github/v/release/Hamza122nr2/macro-studio-updates?style=for-the-badge&color=18A8E6)](https://github.com/Hamza122nr2/macro-studio-updates/releases/latest)
  ![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-18A8E6?style=for-the-badge&logo=windows)
  ![Free to use](https://img.shields.io/badge/Free-to%20use-22C98A?style=for-the-badge)
</div>

![Macro Studio full editor](readme_images/showcase-main-editor.jpg)

Macro Studio can be a quick recorder like TinyTask, or a complete visual automation system with parallel paths, image and color detection, loadouts, jumps, debugging, Discord control, and custom playback interfaces.

## Highlights

- **Three recording styles** ? Smart, Exact, and Raw mouse input for games that lock or hide the cursor.
- **Parallel paths** ? run independent automation paths at the same time and jump between them.
- **Image + color detection** ? capture an image or pixel, restrict the search area, tune match accuracy and polling speed, then branch or jump.
- **Visual organization** ? folders, nested loadouts, collapse states, multi-select, drag/drop, copy/paste, undo/redo, and stable locked targets.
- **Create UI** ? build a separate polished control window from your existing macro without changing its actions or playback order.
- **Debugger mode** ? inspect live steps, detection results, paths, loops, and step through a macro when needed.
- **Discord tools** ? webhooks and optional bot commands for remote control, status, screenshots, and notifications.
- **Mini mode** ? a compact recorder/player when the full editor is more than you need.
- **Resolution-aware playback** ? recorded positions can scale to another display resolution.
- **Recovery and updates** ? automatic crash recovery plus an in-app update flow.

## Create UI: turn a macro into an app-like controller

Create UI is a visual playback layer for the same macro. It does **not** copy, rearrange, or replace actions. Buttons use the macro's existing stable action IDs, loadout controls change the existing loadouts, and Start runs the original macro normally.

![Create UI demo](readme_images/create-ui-demo.gif)

| Design it visually | Use it as the playback controller |
|---|---|
| ![Create UI designer](readme_images/showcase-create-ui-designer.jpg) | ![Create UI runtime](readme_images/showcase-create-ui-runtime.jpg) |

| Nested loadout controls | Live playback information |
|---|---|
| ![Create UI modes page](readme_images/showcase-create-ui-modes.jpg) | ![Create UI monitor page](readme_images/showcase-create-ui-monitor.jpg) |

The designer includes:

- named pages with their own icon and accent;
- sections, labels, action buttons, Start buttons, images, built-in icons, and hover tooltips;
- live status, current action, active path, elapsed time, and loop information;
- nested loadouts with choices, buttons, tiles, or dropdown styles;
- compact templates and full color themes;
- multi-select, group drag, duplicate, internal copy/paste, alignment, layers, and smart snap guides;
- custom window presets including compact, wide, and tall layouts.

The normal global Play/Stop hotkey continues to work while the generated controller is focused. Stopping playback leaves the controller open so it can remain the macro's main interface.

## Download

1. Open the [latest release](https://github.com/Hamza122nr2/macro-studio-updates/releases/latest).
2. Download the Windows ZIP.
3. Follow the one-time **Unblock before extracting** steps below.
4. Open the extracted folder and run `MacroStudio.exe`.

Macro Studio is portable: there is no installer. Updates can be applied from inside the app.

## Important: unblock the ZIP before extracting

Windows marks files downloaded from the internet. If the ZIP is extracted while still blocked, Windows may show warnings for files inside it. Unblock the ZIP first.

### 1. Create a permanent folder and move the ZIP there

Create the folder where you want to keep Macro Studio, move the downloaded ZIP into it, then right-click the ZIP and choose **Properties**.

![Right-click and open Properties](readme_images/1-right-click-properties.png)

### 2. Find the Unblock option

At the bottom of the General tab, the box initially looks like this:

![Unblock unticked](readme_images/2-unblock-unticked.png)

### 3. Tick Unblock

![Unblock ticked](readme_images/3-unblock-ticked.png)

### 4. Click Apply, then OK

After Apply, Windows removes the internet block from the ZIP.

![Properties after Apply](readme_images/4-after-apply.png)

### 5. Extract everything

Right-click the ZIP again, choose **Extract All**, and finish extraction.

![Extract All](readme_images/5-extract-all.png)

After extraction:

- delete the downloaded ZIP;
- keep the extracted Macro Studio folder in its permanent location;
- optionally right-click `MacroStudio.exe` and pin it to Start or the taskbar.

## Default hotkeys

| Action | Default |
|---|---:|
| Play / Stop | `F6` |
| Stop | `F7` |
| Record | `F8` |
| Save | `Ctrl + S` |

Hotkeys, recording mode, playback speed, appearance, Discord controls, sounds, and other behavior can be changed in Settings.

## Source and safety

Macro Studio is **free to use**, but its source code is private. This public repository contains release builds, release notes, documentation, and issue tracking?not the application source.

The Windows build is currently not signed with a paid code-signing certificate, so Windows reputation warnings can still appear on a fresh download. The Unblock steps above prevent the downloaded ZIP marker from being copied into the extracted files.

## Feedback

Found a bug or have an idea? [Open a GitHub issue](https://github.com/Hamza122nr2/macro-studio-updates/issues).

See [CHANGELOG.md](CHANGELOG.md) for the complete release history.
