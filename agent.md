# Agent Instructions

Skills are organized into bucket folders at the repository root:

- `engineering/` - daily code work
- `productivity/` - daily non-code workflow tools
- `misc/` - kept around but rarely used
- `personal/` - tied to personal setup, not promoted
- `in-progress/` - drafts not yet ready to ship
- `deprecated/` - no longer used

Every skill in `engineering/`, `productivity/`, or `misc/` should have a reference in the top-level `README.md`.

Skills in `personal/`, `in-progress/`, and `deprecated/` should stay listed in their category README files, but should not be promoted in the top-level README unless there is an explicit reason.

Each skill entry in the top-level `README.md` must link the skill name to its `SKILL.md`.

Each bucket folder should have a `README.md` that lists every skill in the bucket with a one-line description, with the skill name linked to its `SKILL.md`.

When adding or moving a skill:

1. Put the skill in the appropriate category folder.
2. Ensure the skill has a valid `SKILL.md` with `name` and `description` frontmatter.
3. Update the category `README.md`.
4. Update the top-level `README.md` if the skill belongs to `engineering/`, `productivity/`, or `misc/`.
5. Validate the skill with `quick_validate.py`.
