# COOKED - Browser Wordlist Generator

COOKED is a fully browser-based wordlist generation and data manipulation tool.  
No backend, no API, no cloud dependency: everything runs locally in your browser. ⚡

## Why COOKED?

- 🧠 Visual workflow + simplified mode
- 🔐 Security/recon-friendly transformations
- 🧰 Rich method chaining (`.upper.md5`, `.json[key]`, `.regex[...]`, etc.)
- 🖥️ 100% client-side execution
- 🌗 Dark/Light themes with lightweight animated background

## Features

- ✍️ Pattern syntax engine
- `space` = columns, `,` = values
- Numeric ranges: `1-20`, zero-padded ranges: `01-20`
- Character ranges and repeat operators: `r*5`, `r**5`, `r*2-5`
- Raw literals with backticks to keep spaces/special text: `` `hello world` ``

- 🔗 Method chaining
- Chain methods inline: `` `hello world`.upper.reverse ``
- Nested chains supported: `.title.reverse.sha256`
- Global "apply to all" method pipeline
- Per-column method pipeline (`0:upper;1:lower`)

- 🧪 Method coverage
- String transforms: `upper`, `lower`, `title`, `trim`, `replace`, `split`, `splitindex`, `reverse`, `sort`, `sortu`, `unique`
- Filters: `contains`, `starts`, `ends`, `minlength`, `maxlength`
- Encoding/decoding: `b64e/b64d`, `hexe/hexd`, `urle/urld/urlea`, `jsone/jsonu`, `xmle/xmlu`, `unicodee/unicoded`, `utf16`, `utf16be`, `charcode`
- Hashing: `md5`, `sha1`, `sha224`, `sha256`, `sha384`, `sha512`
- URL parsing: `scheme`, `host`, `port`, `path`, `query`, `keys`, `value`, `domain`, `tld`, `subdomain`, `allsub`, `alldir`, `fragment`
- Credentials extraction: `user`, `pass` (supports both URL creds and `user:pass` lines)
- Advanced helpers: `smart`, `smartjoin`, `leet`, `json[key]`, `regex[pattern]`, `filebase`

- ⚙️ Combine modes
- `Cross-product`: all combinations across columns
- `Line-by-line`: index-based pairing
- `Mutation Wordlist`: typo/mutation expansion mode (JS logic inspired by mutation workflows like dmut/twistrs-style behavior)

- 🧱 Visual workflow editor
- Drag-and-drop style nodes for pattern + transformation flow
- Node linking visuals and workflow arrangement helpers
- Undo/redo, duplicate selected nodes, delete selected nodes
- Auto-arrange and reset layout

- 📚 Discoverability UX
- Method reference modal (search, categories, examples)
- Examples & tutorials modal with one-click apply and run
- Method insertion from modal into workflow
- Help (`?`) hints across options and controls

- 🗂️ Data inputs
- Variables editor
- File-to-variable input mapping (line-based)

- 💾 Local persistence
- Presets saved in `localStorage`
- Load/update/delete presets
- Optional auto-restore of last preset

- 🧼 Dual UX modes
- Advanced Mode: visual workflow experience
- Simplified Mode: focused generation flow for quick usage

- ✅ Built-in test harness
- Browser test mode via `?test`
- Engine + example validation coverage

## Quick Start

### 1) Open directly

Open `cooked.html` in your browser.

### 2) Run with local server (recommended)

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080/cooked.html
```

## Example Syntax

```text
admin,root _,- pass,secret
`hello world`.upper.reverse
`{"name":"john","age":30}`.json[name].upper
```

## Notes

- 🚫 No data is sent to external generation services.
- 💡 Performance-oriented frontend (lightweight animations and constrained output preview).
- 🧩 Repository includes older preview files for safe rollback and experimentation.

## Credits

- Original inspiration: https://github.com/glitchedgitz/cook
- Browser-first UX and workflow implementation in this repository
