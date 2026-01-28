---
name: commit-summary
description: Summarize git commits for a manager. Use when the user asks to summarize commits, create a status update, or prepare notes for their manager.
argument-hint: [since-date]
---

Summarize git commits for a manager-friendly status update.

## Instructions

1. Run `git log --since="$ARGUMENTS" --oneline` to get commits since the specified date
2. If no date is provided, ask the user for a date range
3. Group commits by feature/theme, not by technical implementation
4. Write the summary in plain language that a non-technical manager can understand

## Writing Style

- Focus on **what was delivered**, not **how it was built**
- Avoid technical jargon (no "reducers", "zustand stores", "hooks", "refactors")
- Use action verbs: "Built", "Added", "Fixed", "Improved"
- Group related work under feature headings
- Keep bullet points concise (1 line each)

## Output Format

```markdown
## Summary of completed work

This is an ai-generated summary of [user name]'s git log history since [date range].

**Total Commits:** X

### Feature Name (New Feature)

- What users can now do
- Key capabilities added

### Area Improved

- What got better
- User-facing changes

### Bug Fixes

- Brief description of what was fixed (skip minor/internal fixes or summarize many into one line)

### Deployments

- X production deployments
- X preview deployments
```

## Example Transformations

| Technical                                       | Manager-Friendly                                     |
| ----------------------------------------------- | ---------------------------------------------------- |
| "Refactor job form to use reducer"              | "Rebuilt job form for better reliability"            |
| "Use zustand store to manage draft job storage" | "Added draft jobs so users can save and resume work" |
| "Add hook to query draft jobs"                  | (omit or combine into summary)                       |
| "Fix circular state deps in draft jobs manager" | (omit or combine into "Fixed various bugs")          |
| "Redesign [DB row name] cards"                  | "Redesigned [user facing name] cards"                |
