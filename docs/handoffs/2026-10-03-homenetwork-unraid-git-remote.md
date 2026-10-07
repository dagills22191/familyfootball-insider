Origin: HomeNetwork (`E:\ClaudeProjects\HomeNetwork`), session homenetwork-3e, 2026-10-03.

# This repo now has an on-LAN git remote: `unraid`

**What HomeNetwork did (Tim approved, 2026-10-03):**

- Created a bare repo on the NAS: `\\192.168.1.82\Backups\git\familyfootball-insider.git`
- Added a remote to this repo: `unraid` = `file:////192.168.1.82/Backups/git/familyfootball-insider.git`
- Pushed every branch and tag (`git push unraid --all` and `--tags`). Refs matched afterwards and `git fsck` on the bare copy was clean.
- Added the matching `safe.directory` entry to the global git config on TIMHOME11.

Nothing else was touched: no commits, no file edits, existing remotes unchanged. This note is uncommitted - it is yours to commit or delete.

**Why:** that NAS folder is shipped to Backblaze B2 nightly at 01:00 (Duplicati job `unraidconfig`), so a push there gives this repo an on-LAN copy and an offsite copy.

**The ask:** the copy is only as fresh as the last push. Adopt push-after-commit:

    git push unraid main

and add a line saying so to this repo's CLAUDE.md (HomeNetwork did not edit it - not our file). The remote is on-LAN only; a push from off the home network will fail, which is expected.

Once that is in place, delete this note.
