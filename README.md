# mars-tracker-mirror

Read-only daily snapshot of the MARS tournament tracker at
[mars.simtech.vip](https://mars.simtech.vip).

Auto-published by a Cloudflare Worker cron at 00:01 UTC every day.
**Do not edit by hand** - any manual change will be overwritten on the
next cron tick.

## What lives here

`mirror-snapshot.json` is a single bundle of:

- The day blobs (player session history during the tournament).
- The current leaderboard.
- Roster, lossMaps, daysManifest, statsMeta sidecar.
- Projected views of the decisions, soft-remove, and privacy blobs with
  staff-actor identities stripped.

## What does NOT live here

The Discord-username <-> playerId link table is intentionally withheld.
Everything else in the snapshot is already-public-ish data
(OpenFront.io sessions, MARS clan totals, etc.). When the live tracker
is unreachable, signed-in members fall back to this mirror; the
Discord-enrichment panel on profile pages goes blank in that mode and
restores when the live Worker comes back online.

## Reporting

If you found a real bug or privacy issue, open an issue on the main
tracker repository, not this one.
