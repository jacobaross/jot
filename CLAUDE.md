# qq - Quick Note CLI Tool

A minimal CLI for capturing thoughts instantly from the terminal.

## Usage

```bash
qq "your note here"
```

## Behavior

- Appends the note to a single file: `~/Documents/secondbrain/Quick Notes.md`
- Does not create new files—all notes go to the same file
- Each note is formatted with minimal metadata

## Note Format

```markdown
---

**Fri Dec 27 · 14:32**

your note here
```

### Metadata Fields

| Field | Format | Example |
|-------|--------|---------|
| Day | Abbreviated weekday | `Fri` |
| Date | Month Day | `Dec 27` |
| Time | 24h HH:MM | `14:32` |

The horizontal rule (`---`) separates notes visually in Obsidian.

## Configuration

The target file path should be configurable via:

1. Environment variable: `QQ_FILE`
2. Default: `~/Documents/secondbrain/Quick Notes.md`

## Implementation

- Language: Bash script or small Go/Rust binary
- Single file, no dependencies
- Create the target file if it doesn't exist
- Append a newline after each note for clean spacing

## Install

Place `qq` in `~/.local/bin/` or another directory in `$PATH`.

## Edge Cases

- Empty input: print usage and exit
- Missing target directory: error with helpful message
- Quoted vs unquoted args: accept both `qq "hello world"` and `qq hello world`
