# 🧠 LLM Second Brain — Obsidian + Claude Setup

A persistent, compounding knowledge base built on the [Karpathy LLM-Wiki pattern](https://karpathy.github.io/).
The LLM writes and maintains all files. You curate, explore, and ask questions.
The wiki grows richer with every source ingested and every question asked.

Built for: **coursework · software engineering · research · anything you want to think deeply about.**

---

## Files in this gist

| File | Purpose |
|---|---|
| `CLAUDE.md` | Drop this in your vault root — Claude reads it at the start of every session |
| `llm-second-brain.css` | CSS snippet for Obsidian — Inter font, styled callouts, tables, progress bar |
| `appearance.json` | Obsidian appearance settings (enables the snippet, sets Inter font) |
| `app.json` | Obsidian app settings (readable line length, live preview, fold headings) |

---

## Setup

### 1. Create your vault structure
```
YourVault/
├── CLAUDE.md              ← paste contents from this gist
├── index.md               ← Claude keeps this updated (catalog of all pages)
├── log.md                 ← append-only session log
├── overview.md            ← high-level synthesis of everything
├── raw/                   ← drop source files here (immutable)
├── projects/              ← one page per project (software eng) or course
├── concepts/              ← cross-cutting ideas that appear everywhere
├── readings/              ← paper / book / article summaries
└── decisions/             ← architecture decision records (ADRs)
```

### 2. Install the CSS snippet
- Copy `llm-second-brain.css` into `<YourVault>/.obsidian/snippets/`
- In Obsidian: Settings → Appearance → CSS Snippets → enable `llm-second-brain`

### 3. Apply Obsidian settings
- Copy `appearance.json` and `app.json` into `<YourVault>/.obsidian/`
- Reload Obsidian (Cmd+R)

### 4. Recommended plugins
Install via Settings → Community Plugins → Browse:
- **Spaced Repetition** — flashcard decks from any note (`#flashcard` tag)
- **Excalidraw** — embedded diagrams inside notes
- **Dataview** — query your vault like a database
- **Tasks** — track TODOs across all notes

### 5. Connect Claude (Cowork / Claude Code)
- Point Claude at your vault folder
- Claude reads `CLAUDE.md` on every session start — it knows the schema and will maintain `index.md` and `log.md` automatically

---

## How to use it

**Ingest a source:** Drop a file in `raw/` and say `"ingest [filename]"` — Claude reads it, writes a summary page, and updates the index.

**Ask a question:** Ask anything. Claude reads `index.md`, finds relevant pages, and synthesizes an answer with `[[wikilinks]]` to sources.

**Generate flashcards:** Say `"add flashcards for [topic]"` — Claude adds `#flashcard` cards to the relevant note, picked up by Spaced Repetition.

**Lint the wiki:** Say `"lint the wiki"` — Claude checks for orphan pages, missing cross-references, and contradictions.

---

## Credits
Pattern inspired by [Andrej Karpathy's LLM-Wiki idea](https://x.com/karpathy).
CSS and schema by [@alifatma](https://github.com/alifatma) · feel free to adapt.
