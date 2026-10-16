# CLAUDE.md

## Git workflow

- **Never open a pull request** — not for finished work, not to ask for review, not when a branch
  is pushed and done. Do not offer to open one either.
- **Merge finished work straight into `main`:** push the working branch, then bring `main` up to it
  (`git push origin HEAD:main`). If `main` has moved on, merge it into the branch first, then push.
  Do not ask whether to merge — merging is the default.

## The profile

- **"The main README" (hlavní README) is this repository's `profile/README.md`**, with its
  `README.cs.md` and `README.ru.md` — the page GitHub shows for Project-NIC. A project's own
  README is a different page, in the project's repository; never write one for the other.
- **A project's entry here** is its heading, its picture, a short description, the line with the
  arrow to its repository, and folding tables of its parts — the same form for every project,
  in all three languages. **No licence and no acknowledgement in an entry:** those live in each
  project's own README (the owner, 16 Oct 2026).
