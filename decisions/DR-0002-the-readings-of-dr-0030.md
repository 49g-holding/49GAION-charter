# DR-0002 · Charter mother v0.1.1: the readings of 49GAION/DR-0030

- **Date:** 2026-10-19
- **Decided by:** the governing seat (GOV) of 49GAION
- **Source:** `49GAION/DR-0030` (five readings from the Charter mother), merged on 19 October 2026; its item 6 closes, at this mother's next version, the exceptions of blueprint §11 that it settles.
- **Relation:** builds on DR-0001; it supersedes nothing.

## Decision

1. **Four exceptions settled.** Blueprint §11, items 2 (the code `[ORG]CELL-GOV`), 3 (the gateway's own ports), 6 (the Charter's own parts, signed by the governing seat) and 8 (the restart of the whole Charter) are settled by `49GAION/DR-0030`, items 1, 2, 4 and 5. They stay in §11 by number, each marked as settled, so that later references hold.
2. **The lessons.** Blueprint §12, items 1 to 5, each record the item of `49GAION/DR-0030` that took them up. `upstream/PROPOSALS.md` records that all five drafts were merged.
3. **A new case.** TEST-CH case 51 tests the restart of the whole Charter; it belongs to TEST-CH-GOV v1. It reads `NOT_RUN`.
4. **The check.** `tools/make_cards.py` reads `[ORG]CELL-GOV` under the reading note to Naming Standard R15, only for the Cell carrying the unscoped `[ORG]HOAC-GOV`. It accepts the R16 rule only for the Chief of Staff Cell, and it fails on any other code rule.
5. **The version.** Blueprint `v0.1.1`; every card takes the new version. The Library pin moves only by a pull request to `49GAION-protocol` after this merges.

*Powered by 49GAION*
