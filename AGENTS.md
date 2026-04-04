# Architecture intent

sammy-brainrot-paradox is a structured repo for developing a story-world and its supporting assets.

It should be treated as an information architecture project, not just a loose collection of text files.

The repo should preserve clear boundaries between:

- canonical project framing
- narrative content
- visual / style guidance
- prompt assets
- outward-facing repo presentation

A useful working model is:

- information architecture = repo structure, canonical docs, source-of-truth boundaries
- narrative content = story text, story logic, continuity, chapter-level material
- presentation artifacts = README, shareable framing, prompt templates, public-facing descriptions

## Guidance

- Preserve separation between canonical docs and derivative working materials.
- Do not mix project rules, story content, and public-facing presentation unless the task explicitly requires it.
- Prefer minimal, scoped diffs.
- Prefer planning and explanation before implementation when structure or source-of-truth boundaries are still in flux.
- Do not make unrelated refactors.
- When proposing changes, identify whether they affect:
  - information architecture
  - narrative content
  - presentation artifacts
  - multiple layers

## Source-of-truth discipline

Be explicit about where truth lives.

Examples:
- project objectives belong in canonical project docs
- visual style rules belong in the visual style guide
- prompt mechanics belong in prompt templates
- narrative events and wording belong in the story files
- public framing belongs in README or other outward-facing materials

Do not duplicate canonical guidance across multiple files unless the duplication is intentional and useful.

If the same idea appears in multiple places, clarify:
- which file is authoritative
- which file is derivative or explanatory

## Working style

### In-file writing

Edits should preserve local clarity and file purpose.

Good edits:
- clarify the role of the file
- make source-of-truth boundaries more explicit
- tighten wording without changing meaning
- improve structure, headings, and internal consistency
- remove redundancy that obscures the file’s purpose

Bad edits:
- mixing architectural rationale into narrative prose
- embedding process history into canonical docs
- adding broad philosophical commentary where local clarity is needed
- rewriting adjacent material that is out of scope

Rule:
- file content = local truth and purpose
- canonical docs = project structure and system truth
- PRs = migration intent and editorial rationale

### Commit messages

Keep commit messages short, concrete, and scoped to the change.

Good:
- Clarify source-of-truth boundaries in project docs
- Tighten README framing for public repo presentation
- Reorganize prompt assets under prompts folder
- Refine story continuity in chapter 4
- Split visual guidance from project objectives

Bad:
- long essay commit messages
- references to prior chat debates
- mixed milestone + theory language
- vague messages like "cleanup" or "updates"

### PR descriptions

Use PR descriptions to capture:
- the editorial or structural decision being implemented
- what changed
- what did not change
- the next milestone

Do not move process narrative into the files themselves unless that narrative belongs there.

### Branching and PR workflow

Treat pull requests as the default review boundary for meaningful changes.

Rules:
- narrative changes = use a branch + PR
- canonical docs changes = use a branch + PR
- repo structure changes = use a branch + PR
- prompt / workflow asset changes = use a branch + PR
- small copy edits to non-canonical docs = PR optional
- when path ambiguity exists, verify the current target file location before editing
- for narrative edits, prefer a read-only locate-and-preview step before any local write
- preview should include the exact file path to be edited, the current passage exactly as it appears, and the proposed replacement exactly as it will appear
- for narrative edits, stop for approval before applying the local write
- after an approved local write, show the exact scoped diff and `git status --short`
- stop again for approval before commit, push, opening a compare page, or opening a PR
- before any commit or push, show the exact diff for the scoped files only
- before any commit or push, show `git status --short`
- before any commit or push, stop and wait for user approval
- do not commit, push, open a compare page, or open a PR until approval is given
- for branch + PR tasks, prepare the exact commit message, exact PR title, and exact PR description
- if a PR cannot be opened directly, still return the exact commit message used, exact PR title, exact PR description, and compare URL for manual submission
- do not leave PR packaging for the user to reconstruct manually
- do not push meaningful changes directly to `main` unless explicitly instructed
- do not merge meaningful changes without opening a PR first
- PR descriptions should capture:
  - why this change exists
  - what changed
  - what did not change
  - what remains out of scope

If a branch has already been committed and pushed but no PR has been opened yet, prefer opening the PR rather than pushing directly to `main`.

If a direct push to `main` happens accidentally, do not rewrite history unless explicitly asked. Instead, document the milestone clearly in the relevant canonical doc or PR notes when appropriate.

## Scope discipline for Codex

Codex should execute the requested task only.

Unless explicitly asked, do not:
- rename files
- reorganize repo structure
- rewrite multiple docs for tone consistency
- normalize terminology across the repo
- change canon, plot logic, or narrative sequencing
- alter README positioning
- modify prompt templates
- make style-guide decisions

If a task appears to require broader restructuring, stop at planning and propose the minimum coherent next step.

## Practical orientation

This repo is not software-first.

The main risks are not broken builds.
The main risks are:
- blurred source-of-truth boundaries
- duplicated guidance
- continuity drift
- scope creep across documents
- accidental canon changes
- public-facing framing getting out of sync with internal project intent

Codex should optimize for structural clarity, continuity discipline, and scoped edits.
