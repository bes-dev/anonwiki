# AnonWiki

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

AnonWiki is a fully client-side, PGP-encrypted offline wiki in a single HTML file (`anonwiki.html`) featuring full-text search, a live Markdown editor, and version history.

---

## Features

- **Zero-server, all in-browser**
  Runs entirely offline in any modern browser—no backend required.

- **PGP Encryption**
  Encrypt or decrypt your entire wiki with your own OpenPGP keys.
  - Import an existing public key
  - Generate a new key-pair directly in the browser

- **Live Markdown Editor**
  - Split-view: edit raw Markdown ↔ live HTML preview
  - Toolbar for bold, italics, headings, lists, links, images, code, quotes, horizontal rules
  - Keyboard shortcut: `Ctrl+S` / `⌘+S` to save the current page

- **Full-Text Search with Snippets**
  Powered by Lunr.js (with fallback). Press `Ctrl+K` / `⌘+K` to focus search.

- **Revision History & Revert**
  - Track every change as a patch or snapshot
  - Browse full diff history per page
  - Revert to any prior version (with confirmation prompt)

- **Single-File Save/Share**
  - Embed encrypted data + public key as `<script>` tags
  - **Save Wiki** exports a self-contained `anonwiki.html`
  - **Block Wiki** clears browser storage and reloads

- **Hierarchy & Navigation**
  Organize pages into folders by path, with expandable/collapsible tree.

- **Customizable & Extensible**
  - No build tools required
  - All markup and scripts live in one file
  - Easily fork and extend

---

## Getting Started

1. **Download**
   Clone or download `anonwiki.html` to your machine.

2. **Open in Browser**
   Simply open `anonwiki.html` in any modern desktop browser (Chrome, Firefox, Edge, Safari).

3. **Import or Generate Public Key**
   - Click **Settings** → **Import Public Key**, paste your PGP public key (armored) → **Save**.
   - Or switch to **Generate Key Pair** tab, provide Name/Email & passphrase → click **Generate** → save both public & private keys externally.

4. **Decrypt Existing Wiki Data**
   If `anonwiki.html` contains an encrypted `<script type="application/pgp-encrypted">`, you will be prompted for your **private key** and passphrase on load.

5. **Create & Edit Pages**
   - Click **New Page**, set a path like `folder/page-name`.
   - Use the toolbar or raw Markdown.
   - Live preview updates as you type.

6. **Search**
   - Press `Ctrl+K` / `⌘+K`, type keywords → view colored snippets → click result to navigate.

7. **View History & Revert**
   - Open any page → **History** → browse revisions → **Revert** (confirmation required).

8. **Save & Share**
   - Click **Save Wiki** to export a fresh `anonwiki.html` with embedded data.
   - Share that file—recipients with the matching private key can decrypt.

9. **Clear Local Data**
   - Click **Block Wiki** to wipe `sessionStorage` and reload.

---

## Usage & Keyboard Shortcuts

- **New Page**: Button
- **Edit Page**: Button
- **Save Page**: `Ctrl+S` / `⌘+S` or **Save Page** button
- **Cancel Edit**: **Cancel** button
- **Search**: `Ctrl+K` / `⌘+K`
- **Toggle Fullscreen Editor**: ★ button
- **Save Wiki File**: **Save Wiki** button
- **Clear Storage**: **Block Wiki** button

---

## File Structure

All code, markup, styles, and data live in **one** `anonwiki.html` file:

```txt
anonwiki.html
├─ <style> … </style>                  # CSS for layout, typography, modals, tree, editor
├─ <header> … </header>                # Logo, search input, action buttons
├─ <aside class="sidebar"> …</aside>   # Page tree navigation
├─ <main class="main"> …</main>        # View & Edit sections
├─ <footer> … </footer>                # Footer and copyright
├─ <script id="wiki-data"> …</script>  # Initial unencrypted JSON data (Welcome page)
├─ <script src="marked.min.js">        # Markdown parser
├─ <script src="purify.min.js">        # HTML sanitizer
├─ <script src="lunr.min.js">          # Full-text search engine
├─ <script src="openpgp.min.js">       # PGP encryption library
├─ <script src="diff_match_patch.js">  # Patch/diff engine
└─ <script> …JavaScript core… </script> # All interactive logic

---

## Contributing

1.	Fork the repository
2.	Make your changes in anonwiki.html
3.	Submit a Pull Request

Please ensure your additions do not break the zero-build, single-file philosophy.

---

## License

This project is licensed under the Apache License 2.0.
See the LICENSE file for details.
