# Markdown Cheatsheet (for editing `PH502_2026_Scribe_Toolbox.md` on GitHub)

You don't need to install anything. Open `toolbox.md` in the repo, click the
pencil icon ("Edit this file"), type your changes, click the **Preview** tab
to check how it will look, then scroll down and commit. Everything below
renders automatically — you just type plain text with a few symbols.

## Headings

```markdown
# Biggest heading
## Big heading
### Medium heading (use this for each new toolbox entry)
```

## Bold, italic

```markdown
**bold text**
*italic text*
```
renders as: **bold text**, *italic text*

## Lists

```markdown
- item one
- item two
  - indented sub-item

1. first step
2. second step
```

## Math (this is the important one for us)

GitHub renders LaTeX-style math automatically in `.md` files.

- **Inline math** (within a sentence): wrap in single dollar signs.
  ```markdown
  The eigenvalue equation is $H\psi = E\psi$.
  ```
- **Display math** (its own centered line): wrap in double dollar signs, on
  their own lines.
  ```markdown
  $$
  \int_{-\infty}^{\infty} e^{-x^2}\,dx = \sqrt{\pi}
  $$
  ```
- All the usual LaTeX math commands work: `\frac{}{}`, `\sum`, `\int`,
  `\partial`, Greek letters (`\alpha`, `\lambda`, ...), subscripts/superscripts
  (`x_1`, `x^2`), etc.
- **Common mistake:** forgetting to close a `$...$` pair, or accidentally
  using a single `$` where you meant a currency symbol — this will break the
  rendering for the rest of the line. Check the Preview tab if something
  looks off.

## Code

Inline: `` `like this` `` → `like this`

Block (useful for pasting a bit of numerical code):
````markdown
```python
import numpy as np
print(np.pi)
```
````

## Quotes and sign-offs

```markdown
> ✍️ **Added by:** Your Name, 2026-08-14
```
renders as a visually distinct blockquote — this is our convention for
signing each entry (see `toolbox.md`).

## Horizontal rule (section divider)

```markdown
---
```
Use this between entries to keep the file visually organized.

## Links

```markdown
[link text](https://example.com)
```

## A few tips specific to editing on GitHub

- Always check the **Preview** tab before committing — it's the easiest way
  to catch a broken `$...$` pair or a heading level that doesn't look right.
- Only one person should have the file open in "Edit" mode at a time within
  your team — if two people commit changes to the same part of the file at
  once, GitHub will flag a conflict. Agree beforehand on who's typing.
- Add your entry at the *end* of your module's section, and don't edit
  someone else's entry without checking with them first (small typo fixes
  are fine).
- If you want to draft an entry somewhere more comfortable first (e.g. a
  text editor or even by hand), that's fine — just paste the final version
  into the GitHub editor when you're ready to commit.
