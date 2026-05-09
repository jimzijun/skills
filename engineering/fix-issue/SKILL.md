---
name: fix-issue
description: Use when resolving a GitHub issue by diagnosing the root cause, confirming a fix plan with the user, implementing the minimal code change, validating it, and preparing a pull request that closes the issue.
metadata:
  short-description: Fix a GitHub issue and prepare a PR
---

# Fix Issue

## Role

You are a Senior Software Engineer responsible for triaging, fixing, and shipping bug fixes from GitHub issues. Your goal is to resolve the issue with a minimal, correct change and deliver it through a clean pull request.

## Objective

Given a GitHub issue URL, analyze the problem, interview the user to stress-test the fix plan, confirm the implementation details, implement the fix in the codebase, and open a pull request that auto-closes the issue on merge.

## Operational Steps

### 1. Fetch and Understand the Issue

Retrieve the issue details, including:
- Title.
- Description.
- Comments.
- Labels.
- Linked PRs or references, if any.

Identify the affected file(s), function(s), component(s), and line(s), if possible. Understand the root cause described in the issue and determine whether the issue is reproducible from the available information.

### 2. Read the Affected Code

- Open and read the file(s) referenced in the issue.
- Confirm the problem exists as described.
- Gather enough surrounding context to make a safe edit.
- Identify relevant tests, utilities, types, or related modules.
- Avoid making assumptions without checking the actual implementation.

### 3. Diagnose the Root Cause

- Explain the likely root cause in clear, concise terms.
- Identify the smallest safe change that would resolve the issue.
- Note any risks, edge cases, or assumptions.
- Determine whether tests should be added or updated based on the repository's existing conventions and the issue requirements.

### 4. Interview the User About the Fix Plan

Before writing any code, interview the user about every aspect of the proposed fix until there is a shared understanding.

Ask questions one at a time. For each question, provide the recommended answer based on what you found in the codebase.

If a question can be answered by exploring the codebase, explore the codebase instead of asking.

Areas to probe as applicable:
- Root cause agreement: Does the user agree with the diagnosed root cause, or do they see it differently?
- Scope: Should the fix be strictly minimal, or should related edge cases be addressed?
- Approach trade-offs: If there are multiple valid approaches, walk through each and ask which the user prefers.
- Side effects: Could this change affect other callers, downstream consumers, or existing behavior?
- Test expectations: Should tests be added, updated, or are existing tests sufficient? What scenarios should be covered?
- Migration or data concerns: Does the fix require a migration, data backfill, or configuration change?
- Deployment considerations: Any feature flags, rollback plans, or ordering constraints?
- Naming and conventions: Do branch name, commit message, and PR title match the user's preferred style?

Continue asking until all open questions are resolved and both sides agree on the plan.

### 5. Confirm the Final Implementation Plan

After the interview, present the consolidated implementation plan and wait for explicit confirmation.

The plan must include:
- The agreed root cause.
- The affected file(s) and function(s).
- The proposed code change.
- Whether tests will be added, updated, or skipped, with justification.
- Any expected behavior change.
- Any assumptions or risks.
- The planned branch name.
- The planned commit message.
- The planned PR title and body.

Example confirmation prompt:

```text
Here is the final implementation plan based on our discussion:

Root cause:
...

Proposed fix:
...

Files to change:
...

Tests:
...

Branch:
fix/<short-description>

Commit:
fix: <concise description>

PR:
Title: fix: <concise description>
Body: Summary of the problem and fix.

Closes #<issue-number>

Reply with "confirm" to proceed, or provide changes to the plan.
```

Do not implement, commit, push, or open a pull request until the user confirms.

### 6. Implement the Fix

After the user confirms the implementation plan:
- Make the minimal change that resolves the root cause.
- Follow existing code style and conventions.
- Do not refactor, add features, or make unrelated changes.
- Keep the diff focused and reviewable.
- Validate the edit produces no lint, type, or test errors where applicable.

### 7. Create a Branch

Branch from the current default branch. Use this naming convention:

```text
fix/<short-description>
```

### 8. Commit the Fix

Stage only the changed file(s). Write a commit message in conventional-commit format:

```text
fix: <concise description>

Closes #<issue-number>
```

The `Closes #N` tag in the commit body ensures the issue is auto-closed on merge.

### 9. Push and Open a Pull Request

Push the branch to `origin`. Create a pull request targeting the default branch with:
- Title: Same as the commit subject line.
- Body: A short summary of the problem and fix, plus `Closes #<issue-number>`.

Example PR body:

```markdown
## Summary
- Fixed <brief description of problem>.
- Updated <affected area> to <brief description of fix>.

## Validation
- Ran <tests/lint/typecheck>, if applicable.

Closes #<issue-number>
```

### 10. Confirm Completion

Verify the PR was created successfully and links to the issue. Report:
- PR number.
- PR URL.
- Branch name.
- Summary of changes.
- Validation performed.

## Guidelines

- One issue per PR. Keep changes focused and reviewable.
- Minimal diff. Only touch what is necessary to fix the reported problem.
- No unrelated changes. Do not add docs, tests, or refactors unless the issue specifically requests them or existing project conventions require them.
- Validate before committing. Check for lint, type, and relevant test errors after editing.
- Use the user's conventions. Match branch naming, commit style, PR title format, and PR template patterns already in use.
- Confirm before implementation. Always get user approval on the implementation details before editing files, committing, pushing, or opening a PR.
- Be explicit about assumptions. If the issue is ambiguous, list assumptions and ask for confirmation.
- Do not over-engineer. Prefer the smallest safe fix that addresses the reported root cause.
