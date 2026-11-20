Quote section 2 ("Done when") and section 6 ("How to prove it") of issue #62 verbatim in `.github/pull_request_template.md`, following the repository's PR template process.

## Section 2: Done when

- [ ] Tag v0.2.0 with attestation
- [ ] `ROADMAP.md` task 6.2 is ticked in this pull request, with a changelog row stamped from
      `date -u` and the progress table regenerated.

Source of truth: `ROADMAP.md` section 5, task 6.2. If this issue and that row disagree, the row
is right and this issue is stale.

## Section 6: How to prove it

```
$ gofmt -l .                       # must print nothing
$ go vet ./...
$ staticcheck ./...                # v0.8.2
$ go test ./... -race -count=1
$ govulncheck ./...                # v1.9.0
$ scripts/check_roadmap_touched.sh origin/main
$ scripts/roadmap_progress.sh --check ROADMAP.md
$ scripts/test_roadmap_gate.sh
$ scripts/generate_issues.sh --check
$ scripts/test_issue_shape.sh
```

- Local half: everything in the block above, on your machine, before the pull request opens.
  Paste the real output in the testing section rather than describing it.
- Hosted half: `ci / go`, `ci / vuln` and `roadmap-check / gate` for your pull request. A fork's
  green run is evidence about a fork: merging and anything that reads protected settings needs
  write access here.

Include:
Closes #62

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
