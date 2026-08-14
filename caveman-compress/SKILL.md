---
name: caveman-compress
description: >
  Safely compress prose and memory files into concise Caveman style while preserving technical
  substance, code, URLs, paths, commands, headings, and structure. Use when the user invokes
  /caveman-compress FILEPATH, asks to compress a memory file, or requests shorter project prose.
---

# Caveman Compress

Compress one exact user-named prose file. Reduce filler and repetition while preserving every
technical fact. Do not call an external model or service. Do not search for or modify additional
files.

## Safety workflow

1. Resolve the exact path the user named. Refuse missing, unreadable, empty, or oversized files.
2. Classify the file with `scripts/detect.py`. Compress only natural-language files. Skip code,
   configuration, data, lock, environment, and unknown files.
3. Read the complete original. Before editing, create a recoverable backup outside the source
   directory, preferably under `$XDG_DATA_HOME/caveman-compress/backups/` or
   `~/.local/share/caveman-compress/backups/`. Never overwrite an existing backup silently.
4. Produce a candidate in a temporary location. Keep all protected regions byte-for-byte exact.
5. Validate the candidate with `scripts/validate.py ORIGINAL CANDIDATE`. If validation reports an
   error, do not modify the original. Fix only the candidate and validate again.
6. Apply the candidate to the exact named file with a surgical patch. Re-read the result and report
   the backup path and validation result.

If any step is ambiguous or unsafe, stop and leave the original untouched.

## Remove

- Articles: `a`, `an`, `the`.
- Filler: `just`, `really`, `basically`, `actually`, `simply`, `essentially`, `generally`.
- Pleasantries and hedging.
- Redundant phrasing such as `in order to` → `to` and `make sure to` → `ensure`.
- Repeated statements and connective fluff.

## Preserve exactly

- Fenced and indented code blocks, including comments, spacing, and line order.
- Inline code inside backticks.
- URLs, markdown links, file paths, commands, API names, library names, and protocols.
- Proper nouns, dates, versions, numbers, units, environment variables, and exact error strings.
- Frontmatter, heading text and order, list hierarchy, table structure, and meaningful formatting.
- Negations and qualifiers such as `not`, `never`, `only`, and `except`.

## Compress prose

- Use short precise synonyms: `big` over `extensive`, `fix` over `implement a solution for`.
- Use fragments when meaning stays clear.
- Drop `you should`, `make sure to`, and `remember to`; state the action directly.
- Merge redundant bullets only when hierarchy and all technical substance remain intact.
- Keep one representative example when duplicates carry the same lesson.

Never compress a file named `*.original.md`, and never place a new backup beside the live source
where an automatic skill loader could ingest it.

## Boundaries

Operate only on prose files: `.md`, `.markdown`, `.txt`, `.rst`, `.typ`, `.typst`, `.tex`, or
extensionless files proven to be prose. Never modify source code, configuration, data, lock,
environment, HTML, CSS, SQL, or executable files. If prose and code are mixed, compress prose only.

Return a concise result: changed or skipped, exact target, backup path, and validation status.
