# DR-0001 · The mother repository of the Charter, and its first mother blueprint

- **Date:** 2026-10-19
- **Decided by:** the governing seat (GOV) of 49GAION
- **Sources:** `49GAION/DR-0029` (the Charter in the Library, with three Pods); `49GAION/DR-0024` (a mother repository for a Library part); `49GAION/DR-0028` (the Chief of Staff, written COS); `49GAION/DR-0007` (the root; the tool gateway held in the Charter)

## Decision

1. **This repository.** `github.com/49g-holding/49GAION-charter`, public, is the mother repository of the Library part 49GAION Charter. It holds the mother blueprint only, laid out and checked as a writing repository. The part's instances hold an organisation's gateway log and records in their own runtime and private repositories, so the mother lives here (`49GAION/DR-0024`).
2. **The first mother blueprint.** `blueprint/CH-BLUEPRINT.md` `v0.1.0`, the part's first blueprint, written for any organisation on the 49GAION AIOC template `v1.6.0`. No instance runs yet.
3. **Three Pods.** Gateway, Records and Work, as `49GAION/DR-0029`, item 2 sets, with the governing seat, top management and the Chief of Staff directly under the AIOC.
4. **No AI holds the keys.** The gateway, the registry, the numbering service, the event store, the queue and the router are code. The AI Cells watch, route and raise; none writes a policy, a key, a log, the registry or a stream (Protocol §23, item 7).
5. **The fixed test.** TEST-CH v1, 50 cases, every one `NOT_RUN`. The Library's TEST-CHARTER v1 is kept as cases 1 to 12 (`tests/TEST-CH.md`).
6. **The Library pin.** Once merged, this text is pinned in `49GAION-protocol` `library/README.md` by repository, path, version, commit and SHA-256.

*Powered by 49GAION*
