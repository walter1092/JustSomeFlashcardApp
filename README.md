# Walter's Flashcards

A single-file, browser-based flashcard app with spaced repetition (SRS). Cards and review data are stored locally in your browser, so no server or account is required.

## Quick Start

1. Download `Flashcards_Template.html` from this repository.
2. Copy the file into your module folder and rename it to your module code (for example, `MA3006.html`, `MA3004.html`, `MA2002.html`).
3. Open the file in Chrome, Edge, or Brave.

The app uses the filename as the Deck ID, so `MA3006.html` creates the deck `MA3006`. Each renamed file has its own isolated storage in the browser's IndexedDB.

## Updating the App

Cards and review timers are stored in IndexedDB, not in the `.html` file, so updating the app does not affect your data.

When an update banner appears at the top of the screen, or when you go to **Advanced > Backup > Check App Update**, select **Backup & Download**. The app will:

1. Prompt you to download a **Quick Save** (`.json`) backup.
2. Download the latest `.html` file, already renamed to match your module (for example, `MA3004.html`).

Save the new file over your old one and refresh the browser tab. To roll back, go to **Advanced > Backup > Revert (1 Ver)** and re-download the previous version.

## Syncing Shared Decks

To pull new cards or corrections from a shared `.json` deck while keeping your review timers:

1. Open **Advanced > Backup**.
2. Paste the GitHub `.json` link under **GitHub / Cloud Deck Sync** and select **Check for Updates Now**, or select **Load Local Deck / Settings File (.json)**.
3. Choose an import mode and select **Confirm**.

| Mode | Behavior |
|---|---|
| **Patch & Add** | Adds new cards and updates text and diagrams on existing cards. Personal review timers and streaks are preserved. |
| **Two-Device Sync** | Syncs a Quick Save file between your own devices (for example, PC and phone). The most recently studied or edited version of each card wins. |
| **Add Brand-New Cards Only** | Imports new cards and skips all existing cards. |

## Features

**Card tiers**

- **Concept:** Definitions, derivations, and formulas. These cards also power the **Match** game.
- **Quiz (MCQ):** Multiple-choice questions with semicolon-separated options and LaTeX support.
- **Open-Ended (OEQ):** Active recall with fuzzy keyword auto-grading (`**keyword|synonym**`), a customizable synonym dictionary, and exam formula hints (the `?` button or `H` hotkey).

**Function graph plotter**

Select **Plot Graph** next to any image field in the **Add** tab to plot up to three functions (for example, `sin(x)`, `x^2 - 4`, `u(x-1)`). You can pan and zoom, then attach the graph directly to a card without taking a screenshot.

**Optional cards**

Tick **Optional card** for non-examinable or bonus material. These cards are excluded from **Review Due** sessions.

**Browse and multi-select**

Search by Card ID (`#1788...`) or keyword, filter and print through the **Filters** menu, rename or merge chapters, and bulk-move or bulk-delete cards with **Select**.

**AI card generation**

Use `prompt.txt`, or **Advanced > Backup > Export AI Sample Template**, with any LLM to generate `.json` decks from lecture PDFs. The output can be reviewed before import and imported in one step.x