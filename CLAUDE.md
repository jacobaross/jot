# jjot - Quick Note CLI Tool

A minimal CLI for capturing thoughts instantly from the terminal.

## Usage

```bash
jj
Note: your note here
```

## Behavior

- Appends the note to a single file: `~/Documents/secondbrain/Quick Notes.md`
- Does not create new files—all notes go to the same file
- Each note is formatted with minimal metadata

## Note Format

```markdown
---

**Fri Dec 27 · 2:32 PM EST**

your note here
```

### Metadata Fields

| Field | Format | Example |
|-------|--------|---------|
| Day | Abbreviated weekday | `Fri` |
| Date | Month Day | `Dec 27` |
| Time | 12h with timezone | `2:32 PM EST` |

The horizontal rule (`---`) separates notes visually in Obsidian.

## Configuration

The target file path should be configurable via:

1. Environment variable: `JJ_FILE`
2. Default: `~/Documents/secondbrain/Quick Notes.md`

## Implementation

- Language: Bash script
- Single file, no dependencies
- Create the target file if it doesn't exist
- Append a newline after each note for clean spacing

## Install

Place `jj` in `~/.local/bin/` or another directory in `$PATH`.

## Edge Cases

- Empty input: print message and exit
- Missing target directory: error with helpful message
