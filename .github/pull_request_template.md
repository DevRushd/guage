Quote section 2 ("Done when") and section 6 ("How to prove it") of issue #61 verbatim in `.github/pull_request_template.md`, following the repository's PR template process.

## Section 2: Done when
Done when every document in the repository has been aligned with v0.2 behavior:
- PRD.md, ARCHITECTURE.md, ARCHITECTURE_ESSENTIALS.md, and project_structure.md reflect v0.2 behavior with no v0.1 descriptions that contradict v0.2
- All [Unverified] claims remain marked as unverified unless supported by verification evidence
- No em dashes in documentation, comments, or commit messages
- ROADMAP.md task 6.1 marked complete
- Changelog entry added with UTC date
- Progress table refreshed using `scripts/roadmap_progress.sh`

## Section 6: How to prove it
How to prove documentation alignment with v0.2 behavior:
- Verify that all documentation files have been updated to reflect actual v0.2 behavior (not v0.1)
- Confirm ROADMAP.md task 6.1 is marked `[x]` and its changelog row is present
- Run `scripts/roadmap_progress.sh --check ROADMAP.md` to ensure progress table is current
- Run `gofmt -l .`, `go vet ./...`, `staticcheck ./...`, `go test ./... -race -count=1`, `govulncheck ./...` to verify no regressions
- Search the complete diff for em dashes and confirm none exist
- Confirm `.github/pull_request_template.md` contains the exact required issue sections
- Confirm ARCHITECTURE_ESSENTIALS.md remains within its intended size with v0.2-aligned content
- Verify `[Unverified]` claims were not incorrectly promoted

Include:
Closes #61

## Task IDs

-

## What changed

## How it was tested

Include the exact commands run and their results. State which checks in `AGENTS.md` section 5 do not exist yet.

## Docs updated

- [ ] `ROADMAP.md` updated in this pull request: task boxes, changelog row, progress table, `Last updated`
- [ ] `PRD.md`, `ARCHITECTURE.md`, `ARCHITECTURE_ESSENTIALS.md` and `project_structure.md` updated where behavior or files changed

## Roadmap checkbox

- [ ] `ROADMAP.md` is current for this change
