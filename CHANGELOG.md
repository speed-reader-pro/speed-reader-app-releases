# Changelog

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
