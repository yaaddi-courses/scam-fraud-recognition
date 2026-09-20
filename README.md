# Scam & Fraud Recognition

Spot phishing, fake calls, AI voice cloning, and financial scams before they cost you money — the red flags that actually work, memorized for life.

Part of the [Yaaddi](https://github.com/yaaddi-courses) course catalog — a
spaced-repetition flashcard course, ready to build and validate with the
standard Yaaddi course tooling.

## Structure

- `meta.json` — course metadata (title, description, cover image, version)
- `source/` — authoring source (`meta.csv`, `units.csv`, `cards.csv`, `glossary.csv`, images/)
- the built `.zip` — generated from `source/` via `build_course_zip.py`

## Editing this course

1. Edit `source/units.csv` / `source/cards.csv` / `source/glossary.csv` directly.
2. Run `python validate_course.py . --source` and fix anything it flags.
3. Run `python build_course_zip.py .` to regenerate the shipped `.zip`.
4. Commit both the `source/` changes and the rebuilt `.zip`.

## Sibling course

This course has a native-language sibling, `scam-tashkhis-farsi` — not a
translation, but its own Iran-specific content (fake Sana/subsidy SMS,
card-to-card fraud, messenger account takeover, Telegram investment scams)
sharing the same psychological-foundations deck structure and icon set.
