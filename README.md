# 49GAION Charter · the mother blueprint

The mother repository of the Library part **49GAION Charter**. In an `[ORG]AION`, the part is the AIOC `[ORG]AIOC-CH`, the root of the organisation. This repository is public. It holds the mother blueprint only, for any organisation, with no organisation's data (`49GAION/DR-0024`, `DR-0029`; Naming Standard R9, addition 4).

## What the part does

The Charter is the root of every `[ORG]AION`: the one AIOC with no parent, under which every other part is installed (Standard §1.7, item 13). It holds:
- the Cell of the governing seat and the Cell of top management;
- **the Gateway Pod**: the one tool gateway, through which every tool and engine call of every part passes, with its signature check, engine register, log, stop doors and live sign-in;
- **the Records Pod**: the registry of record types, the one numbering service, the event store that serves every part's records, the projections and their daily check, and the restricted partition;
- **the Work Pod**: the one shared queue of Work Items, with its watchdog, the router and wake.

One of each per `[ORG]AION`. The governing seat installs the Charter and signs every change to it. No AI holds the keys. A stop is never blocked (Protocol §23).

The one-page summary is at the top of the blueprint.

## What is here

| Path | What it is |
|---|---|
| [`blueprint/CH-BLUEPRINT.md`](blueprint/CH-BLUEPRINT.md) | the mother blueprint, `v0.1.1`, on the 49GAION AIOC template |
| [`tests/TEST-CH.md`](tests/TEST-CH.md) | the fixed test, TEST-CH v1: 51 cases, every one `NOT_RUN`, with the Library's TEST-CHARTER v1 kept as cases 1 to 12 |
| [`cards/`](cards/) | the unit cards of its Pods and Cells, and the bot identity cards, generated from blueprint §17 |
| [`decisions/`](decisions/) | the decision records of this repository |
| [`upstream/PROPOSALS.md`](upstream/PROPOSALS.md) | drafts of proposals to 49GAION, not yet proposed |
| [`tools/make_cards.py`](tools/make_cards.py) | generates and checks the cards (case 38) |

## Mother and instance

- **The Library pins this text** by repository, path, version, commit and SHA-256 (`49GAION-protocol`, `library/README.md`). A new version reaches the Library only by a pull request that moves the pin.
- **Each organisation makes its own instance** from it: its writing repository `<org>aioc-ch`, private, with the `<organisation>`, `<org>` and `<filled>` values set (blueprint §0, §2.1). The organisation's values, its gateway log and its records never come back here.

## Checks

On every pull request and on main (`.github/workflows/checks.yml`):

```
python3 tools/make_cards.py <49GAION-protocol>/spec/schemas      # 0 errors; the committed cards are the generated cards
bash <49GAION-protocol>/.github/scripts/no-org-names.sh          # no organisation name, host or prefixed code
```

The checks also find no Persian or Arabic-script character in any tracked file.

*Powered by 49GAION*
