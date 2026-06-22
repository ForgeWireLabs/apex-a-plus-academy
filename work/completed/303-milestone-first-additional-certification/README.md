# 303 - M3: First Additional Certification

> **Status:** ✅ Completed 2026-06-21
> Imported milestone from `tracking/milestones.md#M3`; source preserved.

## M3: First Additional Certification

Status: complete

Candidate:

- CompTIA Network+ (`N10-009`)

Dependency:

- M2 should be complete first unless there is a tactical reason to author content in parallel.

Related:

- `todos/TODO-003-network-plus-starter-track.md`

## Completion Notes

Network+ (`N10-009`) is the first additional certification track after A+ and is
available in the manifest with `order: 2` and the `netplus` ID prefix. Its banks
live under `src/content/network-plus/` and include domains, objectives, lessons,
questions, flashcards, and PBQs.

The original starter-track implementation is recorded in
`work/completed/003-network-plus-starter-track/` and audited in
`audits/AUDIT-2026-06-17-network-plus-starter.md`. Subsequent expansion brought
the track beyond starter status: as of this closeout it validates with 5 domains,
25 complete objectives, 41 lessons, 179 questions, 45 flashcards, and 9 PBQs.

## Verification

- Current target check: CompTIA's Network+ certification page still presents the
  Network+ v9/N10-009 objective set.
- `node scripts/validate-content.mjs --strict-coverage` — passed on 2026-06-21;
  Network+ reports 25/25 objectives complete with at least one lesson and at
  least six tagged questions per objective.
