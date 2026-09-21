# Bible

Kit's Hebrew Bible database + build-your-own-translation website (work in progress).

Public-domain sources only: King James Version, Young's Literal Translation,
the Open Scriptures Hebrew Bible (morphology/Strong's crosswalk), BDB and
Strong's dictionary data. No NIV.

## What the build produced (2026-09-20)

- 264,217 word rows across the 39 books of the Tanakh (Hebrew/Aramaic tokens
  with morphology, book/chapter/verse/position)
- Strong's numbers filled via the OSHB crosswalk: 175,322 of 175,449 words
- KJV: 610,324 words, 409,930 renderings aligned to 134,625 Hebrew words
- YLT: 23,145 verses; 17,347 glosses

## Rebuilding

`bible.db` (SQLite) and `worker-out/` (parsed public-domain sources) are build
artifacts and are not committed. To rebuild:

1. Parse the sources with the scripts under the original `worker-out/`
   layout (`parse_oshb.py`, `decode_ztext.py`/`build_kjv_words.py`,
   `ingest_canonical.py` for the canon word files).
2. Run `python3 assemble_bible.py` — writes `bible.db`.

See `assembly_report.json` and `oshb_crosswalk_report.json` for the last
build's verification numbers, and `NOTATION_LEDGER.md` for the project's
shared vocabulary.
