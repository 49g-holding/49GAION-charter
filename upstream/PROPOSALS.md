# Drafts of proposals to 49GAION

**`[ORG]AIOC-CH` mother blueprint v0.1.0 · 19 October 2026.** These are drafts only. Nothing here is proposed to 49GAION without the word of its governing seat, and then only by pull request, merged by that seat. Each draft is generalised: no organisation's name or data.

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

*Powered by 49GAION*
