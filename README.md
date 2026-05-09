# Skill Hub

Reusable agent skills organized by category. Each skill lives in its own folder and exposes a `SKILL.md` file with valid frontmatter.

Use this repository by linking directly to a skill's `SKILL.md`, or to a category README when you want a browsable index.

## Categories

- [Engineering](./engineering/README.md) - daily code work
- [Productivity](./productivity/README.md) - daily non-code workflow tools
- [Misc](./misc/README.md) - useful but less frequently used tools
- [Personal](./personal/README.md) - personal workflow skills
- [In Progress](./in-progress/README.md) - draft skills
- [Deprecated](./deprecated/README.md) - retained for reference

## Engineering

Skills for code work, issue management, planning, debugging, testing, and architecture.

- [create-issues](./engineering/create-issues/SKILL.md) - Scan a repository for validated code quality findings and create one GitHub issue per unique finding.
- [diagnose](./engineering/diagnose/SKILL.md) - Run a disciplined diagnosis loop for hard bugs and performance regressions.
- [fix-issue](./engineering/fix-issue/SKILL.md) - Resolve a GitHub issue with a confirmed plan, minimal fix, validation, and PR.
- [grill-with-docs](./engineering/grill-with-docs/SKILL.md) - Stress-test a plan against project language and documented decisions.
- [improve-codebase-architecture](./engineering/improve-codebase-architecture/SKILL.md) - Find architecture improvement opportunities using domain language and ADR context.
- [improve-issue](./engineering/improve-issue/SKILL.md) - Improve or decompose an existing GitHub issue into actionable work.
- [prototype](./engineering/prototype/SKILL.md) - Build a throwaway prototype to test a design before committing to it.
- [setup-skills](./engineering/setup-skills/SKILL.md) - Set up per-repo configuration consumed by the engineering skills.
- [tdd](./engineering/tdd/SKILL.md) - Build features or fixes using a red-green-refactor loop.
- [to-issues](./engineering/to-issues/SKILL.md) - Break a plan, spec, or PRD into independently grabbable issues.
- [to-prd](./engineering/to-prd/SKILL.md) - Turn current conversation context into a PRD.
- [triage](./engineering/triage/SKILL.md) - Triage issues through a role-driven state machine.
- [zoom-out](./engineering/zoom-out/SKILL.md) - Explain unfamiliar code from a higher-level system perspective.

## Productivity

General workflow tools.

- [caveman](./productivity/caveman/SKILL.md) - Use ultra-compressed communication while preserving technical accuracy.
- [grill-me](./productivity/grill-me/SKILL.md) - Interview the user about a plan or design until decisions are resolved.
- [write-a-skill](./productivity/write-a-skill/SKILL.md) - Create new agent skills with proper structure and progressive disclosure.

## Misc

Useful tools kept outside the daily workflow.

- [git-guardrails-claude-code](./misc/git-guardrails-claude-code/SKILL.md) - Set up Claude Code hooks to block dangerous git commands.
- [migrate-to-shoehorn](./misc/migrate-to-shoehorn/SKILL.md) - Migrate test files from `as` type assertions to `@total-typescript/shoehorn`.
- [scaffold-exercises](./misc/scaffold-exercises/SKILL.md) - Create exercise directory structures with sections, problems, solutions, and explainers.
- [setup-pre-commit](./misc/setup-pre-commit/SKILL.md) - Set up Husky pre-commit hooks with lint-staged, type checking, and tests.

## Full Catalog

The category READMEs list all imported skills, including personal, draft, and deprecated skills.
