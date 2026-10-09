# Pagezy user guide: source files

- `pagezy-guide.md` is the complete user guide, published on zylio.net/software/pagezy.
- `images/` holds its pictures. Each one's description (the text in `![…]`) doubles as its alt text and caption.
  The blue numbered boxes in a picture match the numbered steps written under it.

## Keeping it up to date

The guide covers every feature. When a feature is added or changed:

1. Update `pagezy-guide.md` (and its Contents list).
2. Add or change the picture's set-up in `scripts/guide_sections.py`, `guide_parts_b.py` or `guide_parts_c.py`,
   then run `python scripts/guide_shots.py` (about two minutes, offscreen, made-up sample files only).
   `PAGEZY_GUIDE_PARTS=edit,organize` runs only some sections; `PAGEZY_GUIDE_ONLY=edit-text` only some pictures.
3. Run `pytest tests/test_guide.py`. It fails when a Home tool, a mode or a keyboard shortcut is missing from the
   guide, when a picture is missing or unused, or when the guide mentions GitHub.

Pushing a change here to `main` also updates the copy on the public releases page (`.github/workflows/public-page.yml`).
