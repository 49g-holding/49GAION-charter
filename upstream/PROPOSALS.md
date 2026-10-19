# Drafts of proposals to 49GAION

**`[ORG]AIOC-CH` mother blueprint v0.1.0 · 19 October 2026.** These are drafts only. Nothing here is proposed to 49GAION without the word of its governing seat, and then only by pull request, merged by that seat. Each draft is generalised: no organisation's name or data.

**Status, 19 October 2026.** On the word of the governing seat of 49GAION, all five drafts below were merged as `49GAION/DR-0030` (hub pull request #79; Protocol pull request #51). They are kept here as history.

## 1. "GOV" in a Cell's code

- **Current text.** Naming Standard R15, item 2: a Cell's code is the initials of the Cell's own name. It gives the example "Top Management Seat" → `[ORG]CELL-TMS`, and none for the governing seat, while the Library has used `[ORG]CELL-GOV` since `v1.5.0` (`49GAION-protocol`: `library/cards/org-aion-top-management.unit-card.json` and the reference organisations).
- **Proposed text.** A reading note to R15, item 2: "The Cell that carries `[ORG]HOAC-GOV` may take the code `[ORG]CELL-GOV`: GOV is the Standard's short form of the governing seat, as COS is of the Chief of Staff (R16)."
- **Reason and evidence.** Blueprint §11, item 2; the card check records the code as an exception.
- **Parts and tests affected.** Naming Standard R15; TEST-CH case 38.

## 2. The ports of the part that holds the gateway

- **Current text.** Every port of every card reads `enforcement: shared-gateway-outside-unit`.
- **Proposed text.** A reading note to the port field: "For the Charter, which holds the gateway, `shared-gateway-outside-unit` reads as enforced by the gateway's own policy, under `change-gateway-policy`, with its log reviewed by the internal-audit line (Standard §4.4, item 11)."
- **Reason and evidence.** Blueprint §11, item 3.
- **Parts and tests affected.** `spec/schemas/unit-card.schema.json` (description only); TEST-CH case 45.

## 3. Two acts for the signature list

- **Current text.** Standard §4.4, item 11: the hash of the signature list the gateway loads equals the Standard's list at its latest released tag plus the organisation's own additions. Item 6: an organisation adds types to its own copy.
- **Proposed text.** Add to item 11: "An addition to the organisation's list is `change-org-standard-or-signature-list`; loading the new list at the gateway is `change-gateway-policy`."
- **Reason and evidence.** Blueprint §4.2 (SOP step 3) and §12, item 3: the two acts are signed by different seats, and neither text names both.
- **Parts and tests affected.** Standard §4.4, items 6 and 11; TEST-CH case 19.

## 4. The restart of a stopped Charter

- **Current text.** Standard §4.3, items 4 and 7, and Protocol §4.9, item 1: a stopped unit restarts only by a human decision, signed by the HOAC above it, never by anything under it; human Cells under a stopped part cannot sign its restart.
- **Proposed text.** Add to Standard §1.7, item 13: "A stop of the whole Charter is lifted as the organisation's constituting documents set, outside the `[ORG]AION`, and recorded in the unit register."
- **Reason and evidence.** The governing seat's Cell is inside the Charter, and nothing is above it, so no seat can sign the Charter's restart (blueprint §11, item 8; §12, item 4).
- **Parts and tests affected.** Standard §1.7, item 13; §4.3; Protocol §4.10, item 11 (`hoac_over`).

## 5. Who signs a change of a part of the Charter

- **Current text.** Standard §1.7, item 13: the Charter is installed and changed only on GOV's signature. Protocol §4.10, item 11: `hoac_over` walks `accountable_to`.
- **Proposed text.** Add to `hoac_over`: "For a change, installation or retirement of a Pod or Cell of the Charter (its parent is the Charter, or a Pod of the Charter), it returns the Cell carrying the unscoped `[ORG]HOAC-GOV`."
- **Reason and evidence.** The Charter's Pods and Cells are accountable to top management (Protocol §23, item 7), so `hoac_over` alone returns top management for a change that the Standard reserves to GOV (blueprint §11, item 6; §12, item 5).
- **Parts and tests affected.** Protocol §4.10, item 11; the reference organisations; TEST-CH case 14.

*Powered by 49GAION*
