# 219 - Release candidate, version, installer, and upgrade audit

> **Status**: Completed 2026-06-22
> **Owners**: Release/QA Specialist lead.
> **Depends on**: 305.

## Intent

Turn the current multi-cert build into a disciplined release candidate instead
of a pile of successful build commands. This item covers the missed release
details: version consistency, latest-stable docs, changelog cut, installer
upgrade behavior, checksums, smoke install, rollback notes, and honest signing
status.

## Scope

In scope:

- README latest-stable/current-release wording.
- `CHANGELOG.md`, `VERSION`, `package.json`, and `src-tauri/tauri.conf.json`
  version consistency.
- Windows installer upgrade behavior from Apex A+ Academy and previous
  SkillForge versions.
- Release-candidate checklist and release audit.
- Checksum generation/verification.

Out of scope:

- Buying/signing with a trusted certificate; 212 remains blocked.
- Mobile release distribution; Android/iOS are 217/218.

## Verification Plan

- `npm run desktop:build`
- Generate or verify SHA-256 checksums for produced installer.
- Fresh install smoke test.
- Upgrade smoke test from prior public installer if available.
- Backup/export/import smoke test.
- Uninstall/reinstall data behavior check.

## Closeout

The release surface now has one coherent version story:

- `package.json`: `1.4.0`
- `src-tauri/tauri.conf.json`: `1.4.0`
- `VERSION`: `1.4.0`
- Local installer: `SkillForge Academy_1.4.0_x64-setup.exe`
- GitHub publication: pending external billing resolution

Evidence:

- `docs/release-candidate-1.4.0.md`
- `audits/AUDIT-2026-06-22-release-candidate-1.4.0.md`
- `evidence/runs/20260622-102314-219-release-candidate.json`
- `src-tauri/target/release/bundle/nsis/SHA256SUMS.txt`

Smoke results:

- Installed app launched successfully.
- Apex A+ Academy `1.2.1` silent install created a legacy uninstall entry.
- SkillForge Academy `1.4.0` silent install removed the Apex uninstall entry,
  installed SkillForge at `1.4.0`, and preserved the shared app-data directory.
- Backup-specific tests passed.

Notes:

- Artifacts remain unsigned while 212 is blocked.
- Interactive manual learner workflow smoke is deferred to 221 and 228.
