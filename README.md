# 49GAION Charter · the mother blueprint

The mother repository of the Library part **49GAION Charter**. In an `[ORG]AION`, the part is the AIOC `[ORG]AIOC-CH`, the root of the organisation. This repository is public. It holds the mother blueprint only, for any organisation, with no organisation's data (`49GAION/DR-0024`, `DR-0029`; Naming Standard R9, addition 4).

> **Reading (49GAION DR-0041).** The complete definition of 49GAION, approved by its governing seat on 25 October 2026, is `49GAION-FRAMEWORK.md` in `github.com/49g-holding/49GAION`. Where this repository differs from it, the definition governs, and this text is read with it. This part is what an organisation's core is made from: the root, at the governance level, holding the governance seat, the organisation's own rules, the governance panel, the gateway and the stop. The Top Management position sits in the Top Management Group, the first AIOC under the core, which is the hub of the operation, human and AI. The readings are in [`decisions/DR-0003`](decisions/DR-0003-the-readings-of-dr-0041.md). Nothing here is removed.

> **Reading (49GAION DR-0041; `decisions/DR-0004`).** The Records and Work Pods are shared services that run as code, like the gateway: holding them is not running the operation, and every record and Work Item stays with the unit that owns it.

> **Reading (49GAION DR-0042; `decisions/DR-0005`).** The gateway and the stop run as code beside the core, outside the reach of every AI, the core's own included; the core's own stop is held by the governance seat. Changes to them count as loosening, and fresh keys are issued at the handover. TEST-CH gains seven cases, five of them must-fail.

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

**The Protocol pin.** The checks are the one set of checks of the Library repositories, the action `library-checks` of `49GAION-protocol`, run at the commit in `PROTOCOL-PIN`, which also gives the schemas and the `no-org-names` scanner they read, never at `main`, so a change in the Protocol changes nothing here until this repository moves the pin by pull request.

On every pull request and on main (`.github/workflows/checks.yml`):

```
python3 tools/make_cards.py <49GAION-protocol>/spec/schemas      # 0 errors; the committed cards are the generated cards
bash <49GAION-protocol>/.github/scripts/no-org-names.sh          # no organisation name, host or prefixed code
```

The checks also find no Persian or Arabic-script character in any tracked file.

## Owner and licence

- **Owner and licence.** The copyright holder, and the licences of the texts (CC BY 4.0, credit "Powered by 49GAION") and of the code (Apache-2.0), are in [`LICENSE.md`](LICENSE.md).

*Powered by 49GAION*
