# Changelog

## [1.1.10]

### Added
- **Prevent display sleep during reading** — the display now stays awake while RSVP playback is active and returns to normal sleep behavior when playback is paused or finished.

## [1.1.9]

### Fixed
- **URL bot-wall fallback reliability** — sites that first return a placeholder and then load the real article now work more reliably, with retry handling for script or DOM delays and better protection against race conditions during navigation.

## [1.1.8]

### Added
- **Read URL from Browser (⌘⇧U)** — the app can now grab the current tab URL from your browser with one shortcut.
- **Browser tab picker in URL tab** — a new picker lets you choose any open browser tab and load it directly.

## [1.1.7]

### Added
- **Reading streak + activity heatmap** — a new Statistics overlay shows your current streak, longest streak, total days read, daily reading minutes, and a 20-week heatmap with color-coded intensity.
- **Cross-session persistence** — reading stats are saved automatically so your streak and activity history stay available between sessions.

## [1.1.6]

### Added
- **Pre-reading time-savings estimate** — before reading starts, the app now shows how much time RSVP will save compared with regular reading.
- **Bot-wall fallback via WebView** — if a site blocks the normal fetch, the app now falls back to an offscreen browser view and continues from the fully loaded page.

### Fixed
- **WebView fallback delay** — the hydration delay now works reliably, so page loading no longer gets stuck.

## [1.1.5]

### Added
- **Performance: large URL loading optimization** — heavy HTML articles now load much faster and no longer freeze the app.
- **Web content blocking** — offscreen page resources like images, styles, fonts, and scripts are no longer fetched when they are not needed.
- **Faster article extraction** — the article parsing code is loaded more efficiently and cleaned up reliably after each run.
- **Better preview performance** — only visible preview blocks are created, which reduces memory use and improves scrolling.
- **Improved image caching** — fetched images are reused more effectively across preview rebuilds.

## [1.1.4]

### Added
- **Manual Plain / Markdown mode for pasted text** — the Text tab now lets you choose the format instead of auto-detecting it.
- **EPUB images, formulas, and tables** — technical eBooks now pause on images, formulas, and tables instead of skipping them.
- **DOCX code blocks** — monospaced paragraphs are now treated as code blocks.
- **Seek starting on a placeholder now pauses** — starting playback on a pauseable block now shows its preview immediately.

### Fixed
- **BookPreview highlighting for images, formulas, and tables** now correctly outlines these blocks during pause.
- **BookPreviewView renders images, formulas, and tables inline** so EPUB/FB2 previews match the other document types.

## [1.1.3]

### Added
- **Auto-pause on visual blocks** — reading now pauses on images, math formulas, tables, and code blocks, with a preview or continue hint shown in the reader.
- **Continue mode setting** — choose between waiting manually or auto-continuing after a set time, with a visible countdown.
- **Lightbox for paused blocks** — paused content can be opened in a larger overlay for easier inspection.
- **Math formulas via KaTeX** — formulas in DOCX, URL articles, and Markdown now render properly as a single reading block.
- **Tables** — DOCX and URL tables now appear as real tables instead of plain text.
- **Code blocks with syntax highlighting** — fenced code and code snippets now render with syntax highlighting.

### Fixed
- **Markdown auto-pause positions** now match the exact visible block.
- **Highlighting inside paused code and tables** now stays on the correct placeholder.
- **DOCX formulas** now render correctly in the preview.
- **URL field locking** prevents switching articles during active reading.
- **PDF links in URL input** are now handled more cleanly and no longer show unnecessary error noise.

## [1.1.2]

### Added
- **⌘F search across all previews** — opens a compact search panel with live highlighting, match count, navigation, and a **Read from here** action.
- **Table of contents** — new chapter sidebar for EPUB, FB2, Markdown, DOCX, PDF, and URL articles; click an entry to jump to that section.

### Changed
- **Unified preview toolbar** — key preview controls are now grouped together in one top row for easier access.

## [1.1.1]

### Added
- **Back-10% / Forward-10% seek** (Shift + ←/→) now in all reading modes: Main window inline reader, Separate-window panel, Notch widget, and External Reader Bar.

### Changed
- **Zen chunked playback** (2+ words) now centers the indicator on the visual middle of the chunk for easier fixation; single-word mode unchanged.

### Fixed
- Play (or Space) during Notch countdown now cancels the overlay and starts playback immediately instead of starting hidden in the background.

## [1.1.0]

### Zen Mode — a new distraction-free reading experience

A fourth reading mode that opens in fullscreen on its own Space. Centered word with optional context, drag-scrub progress, info bar, and the standard playback  
 controls. Esc / ⌘W / Done to exit.

- **Top pause settings** — tweak WPM, font size, words-at-a-time, upcoming-words, auto-hide and loop right from the Zen window when paused.
- **Auto-hide UI** — bottom controls fade out after 2 s of inactivity; mouse or keypress brings them back.
- **Words at a time** — read 1–7 words per beat, classic chunked RSVP. Per-beat timing scales sub-linearly so chunked playback feels noticeably faster than single-word
  at the same WPM.
- **Loop** — auto-restart from the beginning when the article ends.
- **Settings → Zen Mode tab** — font size (24–96 pt), upcoming words, auto-hide.  


### Inline images

Images now render and pause the reader on each picture instead of being silently skipped:

- **URL articles** — images from web pages (including lazy-loaded ones).
- **DOCX documents** — embedded images preserved in document order.  


### External Reader Bar

While reading happens in Notch, Separate Window or Zen, the main window now shows a compact bar with progress, ±word, play/pause, **Show** (brings the reader to front)
and **Stop**.

### Other improvements

- Reading-mode selector now has four cards.
- Zen opens paused — Play / Space starts the session.
- After any pause the reader holds on the current word for 0.6 s before resuming, giving your eye a moment to re-fixate.
- Zen scrubber resumes playback automatically after a drag if the session was playing.  


### Fixed

- Speed settings now stay synchronized between Settings and all reading modes.

## [1.0.9]

- Reading markdown files now flows much more naturally: code blocks, math formulas, images, tables, footnotes, and `:emoji:` shortcodes all render properly in the preview and read at a sensible pace in the RSVP stream — no more crawling through code one token at a time or sailing past pictures silently.
- Markdown documents now have **Preview / Edit** tabs (matching the PDF flow). Edit shows the raw `.md` source for skimming or copying; nothing is written back to the file, and a Reset control restores the original at any time.
- Settings → Contact got a refresh: dedicated **Contact Support** and **Restore Purchases** buttons that take you straight into the in-app customer portal where you can leave a request or sign in by email to recover your license. Email, Website, and a `Made by @khlebobul` credit live in a small footer row.
- Statistics → "Avg Speed" no longer reports impossible numbers (like 5992 WPM). Very short or accidental sessions are now excluded, and the average is bounded by your actual speed setting.
- A handful of richer markdown features now render correctly: inserted/marked text, definition lists, abbreviations with hover tooltips, sub- and superscripts, custom container blocks (warning / info / tip / danger), and typographic replacements (`(c)` → ©, `--` → en-dash, `...` → ellipsis, etc.).

## [1.0.8]

### Changed

- Trial badge is now pinned to the top of the main content area

### Infrastructure

- Homebrew distribution: Speed Reader can now be installed via Homebrew. After this release the cask lives in the new public [`speed-reader-pro/homebrew-tap`](https://github.com/speed-reader-pro/homebrew-tap) repository:

  ```
  brew install --cask speed-reader-pro/tap/speed-reader
  ```

## [1.0.7]

- App icon now renders correctly on all Macs — fixed a safe-area issue that made the icon look oversized with white corners on some displays.

## [1.0.1 - 1.0.6]

- Bug fixes, onboarding improvements, and update mechanism polish.

## [1.0]

- **First public release** of Speed Reader.
