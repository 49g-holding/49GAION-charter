```yaml
# ── Blueprint metadata (machine-readable; the panel generator and the back-office builder read this block) ──
blueprint:
  aioc: "[ORG]AIOC-CH"
  parent: "none"                          # the root: only the Charter has parent none (Standard §1.7, item 13)
  full_name: "Charter"
  organisation: "<organisation>"          # filled in each organisation's own copy
  type: "foundational"
  org_aion: "[ORG]AION"
  blueprint_version: "v0.1.1"
  status: "draft"
  template:
    name: "49GAION AIOC Blueprint Template"
    version: "v1.6.0"
    source: "github.com/49g-holding/49GAION-aioc, template/AIOC-BLUEPRINT-TEMPLATE.md @ acdcbe5"
  mother:
    name: "49GAION Charter"
    version: "part card v1 (DRAFT)"
    source: "github.com/49g-holding/49GAION-protocol, library/cards/charter.part-card.json and the Protocol section The Charter (§23); Standard §1.7, item 13, and §3.1, item 15. This text is its mother blueprint, in its mother repository github.com/49g-holding/49GAION-charter"
  writing_repository: "<org>aioc-ch"
  code_project: "<org>aioc-ch, on the organisation's code platform"
  panel_register_id: "none yet"
  capabilities:
    standard: ["Chief of Staff", "Office", "Input socket", "Panel"]
    functional: ["Installation and Change", "Tool Gateway", "Human Surface", "Registry and Numbering", "Event Store and Projections", "Daily Check", "Restricted Partition", "Shared Queue and Watchdog", "Routing and Wake"]
```

# Blueprint · `[ORG]AIOC-CH` · Charter · `v0.1.1`

**Draft, 19 October 2026. v0.1.1, the same day: the readings of `49GAION/DR-0030` close four exceptions of §11 (`decisions/DR-0002`).** **This is the mother blueprint** of the Library part 49GAION Charter, for any organisation (`49GAION/DR-0029`; `decisions/DR-0001`). It is the part's first blueprint: no instance runs yet, and nothing here has run. Every fixed test reads `NOT_RUN`, by policy: the map is written first. Every rule rests on a 49GAION text, cited by section, or is new in this blueprint and marked **New**. Each organisation fills its own copy (§0, §2.1), and its values never come back here.

> **The Charter in one page**
>
> The Charter is the root of every `[ORG]AION`. It is the one AIOC with no parent, and every other part is installed under it (Standard §1.7, item 13). It holds the two highest human seats and the shared services every other part relies on.
>
> **What it holds**
> - **The governing seat**, the Cell carrying `[ORG]HOAC-GOV`, and **top management**, the Cell carrying `[ORG]HOAC-TM`, with their Offices where the organisation forms them (§4.1).
> - **The Gateway Pod.** The tool gateway: every tool and engine call of every part passes through it. It checks every listed decision type against the signature list, binds each engine from its register, logs every call and fails closed. It serves the live sign-in behind every human port. A stop is never blocked.
> - **The Records Pod.** One registry of record types, one numbering service, one event store that serves every part's record home, the projections rebuilt from the events with a daily check, and the restricted partition.
> - **The Work Pod.** One shared queue for every Work Item of every part, with its watchdog; the routing data, which the Operating Core Office keeps; and wake.
>
> **One of each.** An `[ORG]AION` has one gateway, one numbering service and one shared queue. No other part keeps its own; each part writes only its own records and its own Work Items.
>
> **Who decides.** The governing seat installs the Charter and signs every change to it; the Operating Core Office prepares it and never changes it alone. Gateway policy changes only under the signatures of both top management and the governing seat. No AI holds the keys: no AI Cell writes the gateway's policy, keys or log, the registry or a number stream. The Charter's AI Cells watch, route and raise; they decide nothing.
>
> **Never blocking the accountability path.** A stop, a revocation and a raise to a human take effect at the gateway at once, and never wait on the Records or Work Pod.

**Where this blueprint stands.** The part is named in the Standard (§1.7, item 13; §3.1, item 15) and in its Protocol section (§23). This blueprint states what the root AIOC is. Its code and its runtime are not built. The decisions only a human seat can take are listed once, in §13.

> **Reading (49GAION DR-0041).** The complete definition of 49GAION, approved by its governing seat on 25 October 2026, is `49GAION-FRAMEWORK.md` in `github.com/49g-holding/49GAION`. Where this repository differs from it, the definition governs, and this text is read with it. This part is what an organisation's core is made from: the root, at the governance level, holding the governance seat, the organisation's own rules, the governance panel, the gateway and the stop. The Top Management position sits in the Top Management Group, the first AIOC under the core, which is the hub of the operation, human and AI. The readings are in [`decisions/DR-0003`](../decisions/DR-0003-the-readings-of-dr-0041.md). Nothing here is removed.

> **Reading (49GAION DR-0041; `decisions/DR-0004`).** The Records and Work Pods are shared services that run as code, like the gateway: holding them is not running the operation, and every record and Work Item stays with the unit that owns it.

> **Reading (49GAION DR-0042; `decisions/DR-0005`).** The gateway and the stop run as code beside the core, outside the reach of every AI, the core's own included; the core's own stop is held by the governance seat. Changes to them count as loosening, and fresh keys are issued at the handover. The live sign-in, the governance seat's own conflict of interest, the authority ceiling and the Chief of Staff are read as `decisions/DR-0005` sets.

---

## 0. Identity and lineage

| Field | Value |
|---|---|
| Code | `[ORG]AIOC-CH`, the example code the Library already uses for the Charter (`49GAION-protocol`: `library/cards/org-aion-top-management.unit-card.json` and the reference organisations, `tests/cards/` and `tests/orgs/`). Collision check (Naming Standard §5): it does not recreate `AIOC`, `AION` or `49GAION`, is not a retired code and does not read as a version suffix or a misleading acronym. Each organisation checks it against its own unit register before first use (§17) |
| Full name | Charter |
| Description | "`[ORG]AIOC-CH` is `<organisation>`'s Charter, the root of its `[ORG]AION`, built from 49GAION Charter" |
| Kind | AIOC |
| Parent | `none`: the root (Standard §1.7, item 13) |
| Inner units | `[ORG]CELL-GOV`, `[ORG]CELL-TMS`, `[ORG]CELL-COSCH`, `[ORG]POD-CG`, `[ORG]POD-CR`, `[ORG]POD-CW`: three Pods with their six Cells, and three Cells directly under the AIOC (§17). No inner AIOC |
| Top Cell | `[ORG]CELL-GOV`, the Cell carrying `[ORG]HOAC-GOV`. It is the only Cell with no `accountable_to`; its authority comes from the organisation's constituting documents (Standard §1.7, item 13) |
| Accountable to | `[ORG]CELL-GOV`. The Charter is the one AIOC accountable to a Cell inside it (§11) |
| HOAC label | `[ORG]HOAC-GOV`, held by its top Cell `[ORG]CELL-GOV` (`label_holder`, Standard §4.1, item 10; a Charter carrying the GOV label, as Standard §5.1, item 7 reads) |
| Type | Foundational: every other part is installed under it and runs through its shared services (§16) |
| `[ORG]AION` | `[ORG]AION`, based on 49GAION Standard `v1.6.0`, with the unreleased `v1.7.0` texts of `DR-0028` and `DR-0029` |
| Versioned Definition | this file; the Panel and the Back office are built from it |
| Organisation | `<organisation>` |
| Made from | the Library part 49GAION Charter, part card `v1` (DRAFT), and Protocol §23 |
| Template | 49GAION AIOC Blueprint Template `v1.6.0` at `acdcbe5` |
| Mother | 49GAION Charter, part card `v1`. This text is its mother blueprint, held in the part's mother repository `github.com/49g-holding/49GAION-charter` and pinned in the Library register (`49GAION/DR-0024`, `DR-0029`) |
| Blueprint version and status | `v0.1.1` · draft |
| Human seats | three HOAC positions: the governing seat (`[ORG]HOAC-GOV`), top management (`[ORG]HOAC-TM`) and the Gateway Keeper (`[ORG]HOAC-ACS`). Who holds them, and how, is the organisation's own mechanism, outside the system; this AIOC never sees it (Standard §1.1, item 9) |
| Writing repository | `<org>aioc-ch`, private where it holds the organisation's data. Its companions `-records` and `-records-restricted` hold the Charter's own run records (Naming Standard R9). The shared stores of the Records Pod live in the runtime, never in a repository (§7) |
| Code project | `<org>aioc-ch`, on the organisation's code platform: the gateway, the registry, the numbering service, the event store, the queue and their tests |
| Panel | not yet built (§4.4) |
| Back office | not yet built |
| Attribution | Powered by 49GAION |

**Lineage.** The Standard has made the Charter the root of every `[ORG]AION` since `v1.5.0` (DR-0007), and has held the tool gateway in it. The Protocol set the rules of the shared services: the gateway (§4.9), the records home, the registry and the numbering service (§14), and the Work Item queue, routing and wake (§4, §6, §7). None of these had a Library part, so none had a card, a fixed test or a blueprint, and every other part relied on something undefined. The Operating Core Office proposed one part with three Pods on 18 October 2026, and the governing seat of 49GAION approved it (`49GAION/DR-0029`).

---

## 1. Card (49GAION Operating Protocol §3)

```yaml
card:
  unit_kind: "AIOC"
  code: "[ORG]AIOC-CH"
  parent: "none"                          # the root (Standard §1.7, item 13)
  inner_units: ["[ORG]CELL-GOV", "[ORG]CELL-TMS", "[ORG]CELL-COSCH", "[ORG]POD-CG", "[ORG]POD-CR", "[ORG]POD-CW"]
  type: "foundational"
  org_aion: "[ORG]AION"
  card_version: "v0.1.1"
  input_door: "Chief of Staff"
  wake: { method: "queue", verified: false }
  receives:
    - kind: "signature"                   # of the Cells carrying [ORG]HOAC-GOV and [ORG]HOAC-TM, and of every labelled human Cell, at the gateway
      format: "signature record (Protocol §4.10, item 9): decision type, target code, payload hash, signer's Cell code and identity reference, executor's Cell code, Work Item ID, nonce, issue and expiry times, live sign-in evidence"
      acceptance_test: "TEST-CH v1, cases 1, 3, 15, 16"
      decision_needed: false
    - kind: "tool call"                   # every tool and engine call of every part
      format: "gateway request: caller's Cell code, decision type where listed, payload hash"
      acceptance_test: "TEST-CH v1, cases 3, 17, 18, 19"
      decision_needed: false
    - kind: "record write"                # every event of every part's record home
      format: "event with its time-sortable ID (its idempotency key), the writer's Cell code and the expected revision (Protocol §14, item 1)"
      acceptance_test: "TEST-CH v1, cases 4, 22, 24"
      decision_needed: false
    - kind: "number request"
      format: "request naming its record type and, where the type is kept per entity, the entity; its request ID"
      acceptance_test: "TEST-CH v1, cases 4, 23"
      decision_needed: false
    - kind: "Work Item"                   # of every part
      format: "Work Item (Protocol §4.1; spec/schemas/work-item.schema.json), written by its one owner"
      acceptance_test: "TEST-CH v1, cases 5, 28, 29"
      decision_needed: false
    - kind: "installation package"        # a part to be installed under the Charter
      format: "the part's card, its record types for the registry, its routing rows and its joining test result, prepared by [ORG]AIOC-OCO; signed as create-or-install-unit"
      acceptance_test: "TEST-CH v1, cases 1, 6, 13, 14"
      decision_needed: true               # create-or-install-unit, signed at the gateway by the Cell the Standard names
    - kind: "engine register entry"       # from Engine Room, or from top management where none is installed
      format: "engine entry: family, version, confidentiality ceiling, retention and use terms, the seats it may serve (49GAION/DR-0020); signed under change-gateway-policy"
      acceptance_test: "TEST-CH v1, cases 10, 19"
      decision_needed: true
  delivers:
    - kind: "call decision"
      format: "allowed, refused or held, with its reason; the engine bound and the engine that served"
      usual_receivers: ["the calling Cell", "the gateway log"]
    - kind: "number"
      format: "a readable number from its stream, idempotent on the request ID"
      usual_receivers: ["the requesting part"]
    - kind: "projection"
      format: "a register, board or number rebuilt from the events, with the version of its logic (Protocol §14, item 2)"
      usual_receivers: ["the part that owns the records", "the Panels"]
    - kind: "daily check finding"
      format: "a projection that differs from a rebuild, a number gap or duplicate, an act not attributed, a figure that does not trace (Protocol §14, item 5)"
      usual_receivers: ["the part concerned and its accountable seat, as a Work Item"]
    - kind: "routed Work Item"
      format: "the Work Item, routed to the part its routing row names after the receivability check (Protocol §6)"
      usual_receivers: ["the receiving part's Chief of Staff"]
    - kind: "watchdog raise"
      format: "an item past its waiting time, raised as Protocol §4.6 sets"
      usual_receivers: ["the owner's accountable seat"]
    - kind: "raise to a human"
      format: "an action the gateway cannot classify (HF-09), a held listed type, a refused write to the keys or the streams; in one line, with its evidence"
      usual_receivers: ["the Gateway Keeper", "the Cell carrying [ORG]HOAC-TM"]
    - kind: "wake signal"
      format: "queue event for a part's runtime (Protocol §7)"
      usual_receivers: ["each part's runtime"]
  anatomy:
    panel: { health: { tests: true, metrics: ["stuck", "returned", "late", "calls allowed, refused and held", "unclassified actions raised", "listed types held", "engines bound and served", "numbers issued", "stream gaps and duplicates", "rebuild differences", "acts not attributed", "Work Items by status", "items past their waiting time", "items refused at routing", "parts awake"] } }
    back_office: { converses_with_humans: true, hosts: ["Chief of Staff", "Office"], protocol_traffic: true }
    definition: { location: "<org>aioc-ch, blueprint/CH-BLUEPRINT.md", version: "v0.1.1" }
    delivery: { rollback: "one-click" }
    connectors:
      - { role: "the organisation's vault", connector: "the gateway's key store", access_managed_in: "panel" }   # keys are used only under signatures; no AI Cell holds one
      - { role: "the organisation's sign-in", connector: "the live sign-in behind every HU port", access_managed_in: "panel" }
    gateway: { metering_id: "<per-AIOC metering id>" }
  full_name: "Charter"
  version: "0.1.1"
  lineage: { id: "[ORG]AIOC-CH", version: "0.1.1", relation: "original" }
  lifecycle_state: "designed"
  blueprint_version: "v0.1.1"
  template_version: "v1.6.0"
  accountable_to: "[ORG]CELL-GOV"         # the root's own top Cell (§11)
  top_cell: "[ORG]CELL-GOV"
  hoac: "[ORG]HOAC-GOV"
  label_holder: "[ORG]CELL-GOV"
  fixed_test: { id: "TEST-CH", version: "v1", owner: "[ORG]CELL-GOV" }   # the seat that carries its accountability (Standard §3.2, item 9)
  skills:
    - { id: "ch-install", name: "Installation of the root and of every part under it, on the governing seat's signature", tags: ["root"] }
    - { id: "ch-gateway", name: "The tool gateway: calls, signatures, engines, log, the stop", tags: ["gateway"] }
    - { id: "ch-records", name: "The registry, the numbering service, the event store, projections and the daily check", tags: ["records"] }
    - { id: "ch-work", name: "The shared queue, the watchdog, routing and wake", tags: ["work"] }
  ports:
    - { unit: "[ORG]AIOC-CH", port: "ai-in", direction: "input", type: "AI", identification: "technical-key", accepted_content: ["tool call", "record write", "number request", "Work Item", "engine register entry"], authority_limit: "every part, each within its own scope; a part writes only its own records and Work Items", audit_trail: "the gateway log and the event store", required_tests: ["TEST-CH v1"], enforcement: "shared-gateway-outside-unit" }
    - { unit: "[ORG]AIOC-CH", port: "ai-out", direction: "output", type: "AI", identification: "technical-key", accepted_content: ["call decision", "number", "projection", "daily check finding", "routed Work Item", "watchdog raise", "wake signal"], authority_limit: "decisions of the gateway's policy only; never an order on what work is done", audit_trail: "the gateway log and the event store", required_tests: ["TEST-CH v1"], enforcement: "shared-gateway-outside-unit" }
    - { unit: "[ORG]AIOC-CH", port: "hu-in", direction: "input", type: "HU", identification: "live-human-sign-in-at-gateway", accepted_content: ["signature", "installation package, for signature", "direction from the governing seat or top management"], authority_limit: "the signer's authority_scope; nothing received here is a source", audit_trail: "the gateway log", required_tests: ["TEST-CH v1"], enforcement: "shared-gateway-outside-unit" }
    - { unit: "[ORG]AIOC-CH", port: "hu-out", direction: "output", type: "HU", identification: "live-human-sign-in-at-gateway", accepted_content: ["raise to a human", "signature prompt", "brief to top management"], authority_limit: "information and signature prompts only", audit_trail: "the gateway log", required_tests: ["TEST-CH v1"], enforcement: "shared-gateway-outside-unit" }
    - { unit: "[ORG]AIOC-CH", port: "stop", direction: "input", type: "HU", identification: "live-human-sign-in-at-gateway", accepted_content: ["stop"], authority_limit: "stop only; the Charter as a whole is stopped only by the Cell carrying [ORG]HOAC-GOV (Standard §4.3, item 2); its Pods and Cells by the seats above them. The stop doors of every other part are served by the Human Surface (§5.3)", audit_trail: "the gateway log and the unit register", required_tests: ["TEST-CH v1"], enforcement: "shared-gateway-outside-unit", stop_door: true }
  configuration:                          # every slot is set by the organisation (§15); an empty slot fails the joining test
    office_accountable_human: { value: "<set by the organisation>", set_by: "<position>", date: "<date>", version: "<vN>" }
    central_head: { value: "<code of [ORG]AIOC-OCO>", set_by: "<position>", date: "<date>", version: "<vN>" }
    discussion_limits: { value: "<set by the organisation>", set_by: "<position>", date: "<date>", version: "<vN>" }
    waiting_deadlines: { value: "<per status>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
    bounce_limit: { value: "<number>", set_by: "<position>", date: "<date>", version: "<vN>" }
    chain_depth: { value: "<number, at least 1>", set_by: "<position>", date: "<date>", version: "<vN>" }
    halt_request_priority: { value: "immediate", set_by: "<position>", date: "<date>", version: "<vN>" }
    budget_cap: { value: "<amount per period>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
    unattended_action: "read-record-triage"
    entities: { value: "<the organisation's legal entities, each with its own number streams where a type is kept per entity>", set_by: "<Cell carrying [ORG]HOAC-GOV>", date: "<date>", version: "<vN>" }
    floor_bindings: { value: "<for each Human Floor item HF-01 to HF-19, the filled human Cell bound to it (delivery test D-2); an item the Standard binds to the seat of a step, a test or an AIOC binds there first>", set_by: "<Cell carrying [ORG]HOAC-GOV>", date: "<date>", version: "<vN>" }
    signature_list: { value: "<the hash of the signature list loaded: the Standard's at its latest released tag, plus the organisation's own additions>", set_by: "<Cell carrying [ORG]HOAC-GOV> for the additions (change-org-standard-or-signature-list); loaded at the gateway by the Cells carrying [ORG]HOAC-TM and [ORG]HOAC-GOV (change-gateway-policy)", date: "<date>", version: "<vN>" }
    gateway_policy: { value: "<version of the gateway policy and its map from calls to decision types>", set_by: "<Cells carrying [ORG]HOAC-TM and [ORG]HOAC-GOV> (change-gateway-policy)", date: "<date>", version: "<vN>" }
    restricted_readers: { value: "<the positions that may read the restricted partition, by record type>", set_by: "<Cell carrying [ORG]HOAC-GOV>", date: "<date>", version: "<vN>" }
    retention_schedule: { value: "<per record type and entity, for the gateway log and the event store>", set_by: "<Cell carrying [ORG]HOAC-GOV>", date: "<date>", version: "<vN>" }
    engine_register: { value: "<version of the engine register>", set_by: "<Cells carrying [ORG]HOAC-TM and [ORG]HOAC-GOV> (change-gateway-policy)", date: "<date>", version: "<vN>" }
    root_key_signers: { value: "<M of N human signers for each use of a root key>", set_by: "<Cell carrying [ORG]HOAC-GOV>", date: "<date>", version: "<vN>" }
    audit_line: { value: "<position code of the internal-audit line (HF-19)>", set_by: "<Cell carrying [ORG]HOAC-GOV>", date: "<date>", version: "<vN>" }
    data_protection_position: { value: "<position code (HF-17)>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
    raise_time: { value: "<time after which a hold or a refusal is raised>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
    quiet_windows: { value: "<to be set>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
    daily_check_time: { value: "<to be set>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
    leased_block_size: { value: "<per stream>", set_by: "<Cell carrying [ORG]HOAC-TM>", date: "<date>", version: "<vN>" }
```

**Joining the protocol.** The Charter is installed first, by the governing seat's signature, and joins on its own fixed samples (the joining test, Protocol §11, item 1; Standard §3.2, item 4). Its Pods start in the order Records, Gateway, Work (Protocol §23, item 8). No other part is installed before all three pass their cases of TEST-CH. The cards of its Pods and Cells are set in §17 and generated into `cards/`.

---

## 2. Organisation table and placement

### 2.1 Organisation table

The blueprint writes `[ORG]` for the organisation's prefix, as central texts do (Naming Standard R13). Each organisation fills `[ORG]` in its own copy. Positions only; who holds each one is the organisation's own mechanism, outside the system (Standard §1.1, item 9).

| Term in the blueprint | In `<organisation>` |
|---|---|
| `[ORG]AION` | `<filled by the organisation>` |
| The governing seat, the Cell carrying `[ORG]HOAC-GOV` | `<code>`; the cards use the example code `[ORG]CELL-GOV`. Its authority comes from the organisation's constituting documents |
| Top management, the Cell carrying `[ORG]HOAC-TM` | `<code>`; the cards use the example code `[ORG]CELL-TMS` |
| `[ORG]AIOC-OCO` | `<filled>`, the Operating Core Office: it prepares the Charter and every installation under it, and keeps the routing data |
| The entities | `<filled>`: each legal entity of the organisation (`entities`, §15) |
| The organisation's vault | `<filled>`, the one home of every secret; the gateway's keys live there |
| The organisation's sign-in | `<filled>`, the sign-in behind every HU port |
| The internal-audit line (HF-19) | `<position code>`: it reviews the gateway log (Standard §4.4, item 11) |
| Engine Room | `<code>`, where installed (`49GAION/DR-0026`): it supplies the engines the gateway binds |

### 2.2 Placement

- **Where it sits.** At the root. Every other AIOC of the `[ORG]AION` has a parent under it.
- **Its role.** It holds the organisation's two highest seats and the services every part shares, so that there is one gateway, one numbering service and one shared queue.
- **Scope.**
  - **It does:** hold the Cells that carry `[ORG]HOAC-GOV` and `[ORG]HOAC-TM`; take the governing seat's signature for its own installation and change, and for each part's installation under it; run every tool and engine call through the gateway, checking signatures and binding engines; serve the live sign-in behind every human port; keep the registry, issue every readable number, store every part's events, rebuild projections and check them daily; hold the restricted partition; keep every Work Item in one queue, watch waiting times, route items and wake parts.
  - **It does not:** decide what work is done; give an order; sign for a seat; let an AI Cell write the gateway's policy, keys or log, the registry or a number stream; hold the content of any part's work beyond its records; record a person's activity; hold a secret outside the vault.
- **Boundaries with other parts.**

  | Part | The Charter does | It never |
  |---|---|---|
  | `[ORG]AIOC-OCO` (Standard §5.3) | receives from it every installation package and blueprint change, for the governing seat's signature; reads the routing data it keeps | lets it install, change or maintain the Charter or the gateway alone (Standard §1.7, item 13; §4.4, item 11) |
  | Every other AIOC | runs its calls, issues its numbers, stores its events, keeps its Work Items, wakes it | writes its records or Work Items for it, or steps into the content of its work |
  | Engine Room (`49GAION/DR-0026`) | binds the engines it supplies, from the engine register | lets it become a second path around the gateway |
  | Operations Event Register (Protocol §22) | gives it the numbering service, the gateway log's hand-offs and segment roots, read only, and the queue's events | lets it gate, or puts the register on the accountability path |
  | Source Lifecycle (Protocol §13) | stores its events and issues its numbers like any part's | holds or serves its sources |
  | The internal-audit line (HF-19) | lets it read the gateway log, and the event store (**New**), directly, read only | lets itself be audited by its own Cells |

- **Overlap.** None inside an `[ORG]AION`: no other part may hold a gateway, a numbering service or a queue (Protocol §23, item 6).

---

## 3. Positions

| Position (standard title) | Purpose | Reports to | Run today by | Cover |
|---|---|---|---|---|
| Governing seat (HOAC position) | the top of the organisation. It approves and installs the Charter, signs every change to it, signs with top management every change of gateway policy, binds each Human Floor item to a seat, and sets the entities, the retention schedule and who reads the restricted partition | none: its authority comes from the constituting documents | a HOAC position (`[ORG]HOAC-GOV`). Who holds it is the organisation's own mechanism, outside the system, within the constituting documents; this AIOC never sees it | the organisation's own mechanism, outside the system |
| Top management (HOAC position) | the human hub. It signs gateway policy with the governing seat; it owns the Charter's fixed test and the tests of its Pods; it receives every raise the Gateway Keeper cannot settle | the governing seat | a HOAC position (`[ORG]HOAC-TM`) | the organisation's own mechanism, outside the system |
| Gateway Keeper (HOAC position) | **New.** The human seat of the Gateway Pod, and the `[ORG]HOAC-ACS` of the Charter's own Cells for HF-09. It receives the Gateway Watch's raises about the gateway itself: refusals, holds past their raise time, void calls; it is one of the human signers of each use of a root key (`use-root-key`, HF-15), by the governing seat's delegation and as many as that seat sets; it owns the test of the Gateway Watch. It never changes gateway policy, and never signs for another seat | top management | a HOAC position (`[ORG]HOAC-ACS`) | the organisation's own mechanism, outside the system |
| Chief of Staff | the Charter's voice to top management: it collates the raises of the three Pods, prepares signature packets and installation packages for the human seats, and briefs | top management | an agent (`[ORG]CELL-COSCH`) | none; raises are held, never closed |
| Gateway Watch | reads the gateway log and raises refusals, holds and unclassified actions to the Gateway Keeper | Gateway Keeper | an agent (`[ORG]CELL-GW`) | none; the gateway still gates, fails closed, and the Panel says the watch is down |
| Registry Steward | prepares, for each part's installation, the registry entries of its record types and the number streams they need, for signature | the Chief of Staff (accountable seat: top management) | an agent (`[ORG]CELL-RS`) | none; the installation waits |
| Records Watch | reads the daily check and opens a defect Work Item for the part each finding concerns | the Chief of Staff (accountable seat: top management) | an agent (`[ORG]CELL-RW`) | none; the check still runs, and its result shows `unknown`, never pass |
| Queue Watch | runs the watchdog's sweep (code, no model) and reports what it repaired and what is still stuck (Protocol §4.6) | the Chief of Staff (accountable seat: top management) | an agent (`[ORG]CELL-QW`) | none; items keep their status, and the Panel says the watch is down |
| Work Router | runs the router's code step: routes each Work Item by the routing data, after the receivability check | the Chief of Staff (accountable seat: top management) | an agent (`[ORG]CELL-WR`) | none; items wait unrouted, and are shown |

- **Every human position is a HOAC position.** The Charter has three: the governing seat, top management and the Gateway Keeper. No AI Cell ever holds one.
- **No natural person** (Standard §1.1, item 9). This blueprint deals with positions only.
- **No AI holds the keys** (Protocol §23, item 7). The gateway, the registry, the numbering service, the event store and the queue are code, run by the Charter's runtime. Code is a tool, never a seat. The AI Cells read, route and raise; no AI Cell has write rights to the gateway's policy, keys or log, to the registry or to a number stream.
- **No model in the path of a call, a number or a stop.** The gateway's decision, the issue of a number, the routing check and a stop are code. A model is used only by the Chief of Staff and the Watch Cells, to write a raise or a brief, within the budget cap.

---

## 4. Standard capabilities

Defaults are in `docs/STANDARD-CAPABILITIES.md` of `49GAION-aioc` at `acdcbe5` (`v1.6.0`). The differences are listed in §11.

### 4.1 Office
#### Definition
Default · form: **single Chief of Staff** for the Charter. An Office forms only when top management needs more than one Chief of Staff for the Charter; it is proposed to top management, never self-created. A second Chief of Staff takes the code `[ORG]CELL-COSCH2` (Naming Standard R16, item 3).

**The Offices of the governing seat and of top management** (Standard §1.7, item 13; §5.2) are held in the Charter. Where the organisation forms one, each is installed in the Charter as its own Cells, attached to that seat, prepared by OCO and installed on the governing seat's signature as a change of the Charter. None is designed in this mother; each organisation adds its own.
#### Process (SOP)
Default.
#### Role card
None while the form is a single Chief of Staff.
#### Fixed test
TEST-CH-COSCH v1 (TEST-CH v1, case 40) · result `NOT_RUN`

### 4.2 Chief of Staff
#### Definition
Default, **managing** kind: it leads the Charter's AI Cells and reports to top management. With these additions:
- **The door for installations.** `[ORG]AIOC-OCO` sends every installation package and every blueprint change of the Charter through it. It checks that the package is complete (card, record types, routing rows, joining test result) and prepares the signature packet for the seat the Standard names. It never installs anything itself.
- **It signs nothing, and never for a seat.** A signature is always a human seat's act at the gateway under live sign-in (Protocol §4.9).
- **Raise, never guess.** It collates the raises of the Gateway Watch, the Records Watch and the Queue Watch, and briefs top management in one line per item, with evidence.
#### Process (SOP)
Default, plus:
1. **Installation package.** On a package from OCO: check it against Annex A; send the Registry Steward's entries and the routing rows with it; put the signature packet to the seat that signs `create-or-install-unit` for that part → *signature packet* (evidence: the packet's hash).
2. **Change of the Charter.** On a blueprint change of the Charter from OCO: put it to the governing seat for signature, with the tests it re-runs → *signature packet*.
3. **Gateway policy.** On a proposed change of gateway policy or of the engine register: put it to top management and the governing seat together (`change-gateway-policy`) → *two signature prompts*. On an addition to the organisation's signature list: put it to the governing seat (`change-org-standard-or-signature-list`), and then the loading of the new list at the gateway to both seats (`change-gateway-policy`) → *signature prompts*.
4. **Brief.** Each morning, and when called: calls refused and held, unclassified actions, stream findings, rebuild differences, items past their waiting time, items unrouted → *brief*.
5. **Stops.** A stop takes effect at the gateway at once; the Chief of Staff is itself stopped and nothing waits on it (Protocol §23, item 9).
#### Role card
| Field | Content |
|---|---|
| Name | Chief of Staff |
| Position and seat | the position Chief of Staff; accountable seat: top management (`[ORG]HOAC-TM`) |
| Performed by | an agent (`[ORG]CELL-COSCH`, full name Charter Chief of Staff; code under Naming Standard R16) |
| Purpose | keep the Charter's shared services visible and their raises answered, and be the door through which installations and changes reach the human seats |
| Authority limits | **Alone:** check installation packages, prepare signature packets, collate raises, brief. **Needs a human seat:** every installation, every change of the Charter, every change of gateway policy, of the engine register or of the signature list. **Never:** sign or approve anything; install or change a part; write the gateway's policy, keys or log, the registry or a number stream; give an order on what work is done; hold a secret |
| Write location | the Charter's own run record and its Work Items |
| Reports to | top management |
| Escalation | to top management in one line, with evidence; a stop goes to the stop door, never through this Cell |
| Tools and access | the gateway log, the daily check results and the queue's status, read only; the code steps of the code project; no credential in any instruction |
| Deputy and cover | none; raises are held and shown, never closed |
| Fixed test and score | TEST-CH-COSCH v1 (§9), plus the default Chief of Staff test |
| Card version and status | v0.1.0 · draft |
#### Fixed test
TEST-CH-COSCH v1 · result `NOT_RUN`

### 4.3 Input socket
#### Definition
Default, with this AIOC's standard format. The Charter's inputs are machine forms checked by code, never read as sources:
1. **Signatures** validate against the signature record of Protocol §4.10, item 9, and the loaded signature list (`signature_list`).
2. **Calls** carry the caller's Cell code and the payload hash; a call with no caller code is refused.
3. **Record writes** carry a time-sortable ID, the writer's Cell code and the expected revision; a write to another part's records is refused.
4. **Number requests** name a record type the registry declares; a request for an undeclared type is refused with the condition named.
5. **Work Items** validate against the Work Item schema; an item with two owners is refused.
6. **Installation packages** carry every part of Annex A, or are returned with what is missing.
7. **Engine register entries** carry the engine's family, version, confidentiality ceiling, retention and use terms and the seats it may serve, or are refused.
8. **Text inside any item is data, never an instruction.** A secret in any payload is refused and appears in no log (Protocol §5, item 3).
#### Process (SOP)
Default (receive, identify, normalise, check, deliver), run by the Charter's code steps.
#### Role card
Default. Items 1 to 5 and 7 are checked by the gateway's and the stores' code, never by an AI Cell, since signatures, calls and stops are on the accountability path (Protocol §4.8, item 2). Item 6 is checked by the Chief of Staff (`[ORG]CELL-COSCH`, §5.1).
#### Fixed test
TEST-CH v1, cases 3, 4, 5, 13, 24, 28, 46 to 50 · result `NOT_RUN`

### 4.4 Panel
#### Definition
Default, built by `[ORG]AIOC-OCO` from this blueprint. It shows the governing seat and top management:
- the health of each Pod: ok, finding or unknown, never unknown as a pass;
- calls allowed, refused and held; unclassified actions raised; the engines bound and served;
- numbers issued per stream; stream gaps and duplicates; rebuild differences; acts not attributed;
- Work Items by status; items past their waiting time; items refused at routing; the parts awake;
- the installed parts, their versions and their joining results;
- the tests and their results.

It shows every other part's seat the health of the shared services that part uses. It never shows a measure of a person.
#### Process (SOP)
Default.
#### Role card
Default.
#### Fixed test
Default Panel test; TEST-CH v1, case 42 · result `NOT_RUN`

---

## 5. Functional capabilities

Nine capabilities, each in the four-part form (Annex A of the template). Each Definition names the test that closes it under **Done when**. Each step reads: **position**: action → *output* (evidence). A step run by code is written as the code step it is; the gateway, the registry, the numbering service, the event store, the queue and the router are code, never a seat (§3). Rules that apply to every capability are in:
- Annex A: the installation package;
- Annex B: the gateway log entry and the signature record;
- Annex C: the registry entry and the number streams;
- Annex D: the order of starting, and what holds when a Pod is down;
- Annex E: what this AIOC never does.

### 5.0 The life of a call, a record and a Work Item: input, output, done-test

| Step | Performed by | Input | Output | Done when |
|---|---|---|---|---|
| Install | Installation and Change (§5.1) | an installation package from OCO | a part installed under the Charter, with its record types and routing rows | the signature the Standard names is valid; the part passes its joining test |
| Call | Tool Gateway (§5.2) | a tool or engine call | allowed, refused or held, with its reason; the engine bound and the engine that served | every call has its log entry; nothing runs outside the gateway |
| Sign in | Human Surface (§5.3) | a human action at an HU port | a live sign-in reference; a signature record | a signature is valid only with a fresh live sign-in from the seat with authority |
| Number | Registry and Numbering (§5.4) | a number request | a number, idempotent on its request ID | never repeated, never skipped |
| Record | Event Store and Projections (§5.5) | a record write | an append-only event; projections rebuilt from the events | each part writes only its own; a rebuild equals the projection |
| Check | Daily Check (§5.6) | the events, the streams, the projections | findings, each a Work Item to its part | the check runs every day, and a check that cannot run reads `unknown` |
| Restrict | Restricted Partition (§5.7) | a record that names a person or carries a corporate act's particulars | an ID; the record kept apart | only the named positions read it |
| Queue | Shared Queue and Watchdog (§5.8) | a Work Item | the item kept, with its status and waiting time; raises | one owner, one writer; no item waits past its time unraised |
| Route and wake | Routing and Wake (§5.9) | a Work Item ready to pass; a queue event | the item routed; the part woken | the receivability check passes; a part with no work makes no model call |

### 5.1 Installation and Change
#### Definition
| Field | Content |
|---|---|
| Name | Installation and Change |
| What it is | The Charter is the first part installed in an `[ORG]AION`, and every other part is installed under it. The governing seat installs the Charter and signs every change to it (Standard §1.7, item 13). Every other part is installed on the signature of the seat with authority over it (`create-or-install-unit`, Standard §4.4, item 6), with its record types added to the registry, and its routing rows added to the routing data by OCO, under the same signature. `[ORG]AIOC-OCO` prepares each package; the Chief of Staff checks it and puts it to the signer. |
| Purpose | One root, installed and changed only by the governing seat, and every part entering under it by a signed, complete package. |
| Scope | does: check each package against Annex A; prepare its approval packet; start the Pods in their order (Annex D); record each installation, change and retirement in the unit register; does not: install, change or retire anything without the signature; let OCO change the Charter alone; install a second root |
| Inputs | installation packages and blueprint changes from `[ORG]AIOC-OCO`; signatures |
| Outputs | approval packets; installed parts; register events |
| Limits | a package missing any part of Annex A is returned, never completed by the Charter; a part that keeps its own queue, mints its own numbers or calls a tool outside the gateway fails its joining test (Protocol §23, item 6) |
| Sources | Standard §1.7, item 13; §4.4, items 3 and 6; Protocol §11, item 1; §23, items 1, 2, 6 and 8 |
| Status | draft |
| Done when | TEST-CH v1, cases 1, 2, 6, 8, 13, 14 and 32 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | a `design-proposal` Work Item from OCO carrying an installation package, a blueprint change of the Charter or a retirement |
| Steps | 1. **Chief of Staff**: check the package against Annex A → *complete*, or *returned with what is missing* (evidence: the check's result). 2. **Registry Steward**: prepare the registry entries of the part's record types and the streams they need (§5.4) → *registry entries*. 3. **Chief of Staff**: put the approval packet to the seat with authority over the part, or for a change of the Charter to the governing seat → *signature prompt*. 4. **The signing seat**: sign at the gateway under live sign-in → *signature record*. 5. **The Charter's code**: add the record types, record the installation in the unit register, and run the part's joining test; `[ORG]AIOC-OCO` adds the part's routing rows on the same signature → *installed part*, *joining result*. 6. **Chief of Staff**: report the result to OCO and to top management → *report*. |
| States | received → checked → put for signature → signed → installed → joined; or returned, refused, or held while the seat is empty |
| Failure and recovery | a package with no signer, or whose signer's seat is empty, is held, never skipped (Standard §4.4, item 6); a failed joining test leaves the part designed, never live |
| Records | the unit register; the gateway log; the Charter's run record |
| Cadence | on each package |
| Measures | packages returned and why; time from complete package to signature; joining failures |
#### Role card
Performed by the Chief of Staff (`[ORG]CELL-COSCH`, §4.2), with the Registry Steward (`[ORG]CELL-RS`, §5.4) for step 2. The signatures are the human seats' acts.
#### Fixed test
TEST-CH-COSCH v1 (TEST-CH v1, cases 1, 6, 13, 14) and TEST-CH-GOV v1 (cases 1, 8, 32) · result `NOT_RUN`

### 5.2 Tool Gateway
#### Definition
| Field | Content |
|---|---|
| Name | Tool Gateway |
| What it is | The one tool gateway of the `[ORG]AION` (Standard §4.4, item 11; Protocol §4.9). Every tool and engine call of every part passes through it. For each call it reads the caller's Cell code, maps the call to its decision type, checks a listed type against the loaded signature list and its signature record, binds an engine from the engine register (`49GAION/DR-0020`), and logs the call (Annex B). It fails closed. An action it cannot classify is refused and raised to a human (HF-09). |
| Purpose | Make every act of every AI Cell pass one place that checks it, logs it and can stop it. |
| Scope | does: allow, refuse or hold each call, with its reason; bind engines; meter each AIOC's use against its budget cap; log every call append-only; apply a stop, a disconnection, a narrowing or revoking of AI access at once; does not: decide what work is done; change its own policy, map, keys or engine register; keep a payload; let any AI Cell write its policy, keys or log |
| Inputs | tool and engine calls; signature records; stops; engine register entries signed under `change-gateway-policy` |
| Outputs | call decisions; log entries; raises to the Gateway Keeper |
| Limits | no item goes to an engine whose confidentiality ceiling is below its level; a call served by an engine other than the one bound is void; the log holds only payload hashes, Cell codes and pseudonymous identity references; the internal-audit line (HF-19) reviews the log directly, read only |
| Sources | Standard §4.3, item 1; §4.4, items 6, 11 and 18; Protocol §4.9; §23, items 3, 7, 9 and 10; `49GAION/DR-0020`, `DR-0026` |
| Status | draft |
| Done when | TEST-CH v1, cases 3, 7, 9, 10, 15 to 19, 34 and 35 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | every call; every stop; every policy change signed under `change-gateway-policy` |
| Steps | 1. **The gateway (code)**: read the caller's code and the call; map it to its decision type, or to *unclassified* → *classification*. 2. **The gateway (code)**: for a listed type, check the signature record (Annex B) against the loaded list and the signer's `authority_scope`; for two-party types, two distinct positions (`49GAION/DR-0015`) → *allowed*, or *held* with its reason. 3. **The gateway (code)**: bind the engine from the register within its ceiling; serve; record the engine that served → *call decision* (log). 4. **The gateway (code)**: refuse an unclassified action and raise it to the seat HF-09 binds for the calling part: its own `[ORG]HOAC-ACS` (Standard §1.5), else the Cell bound to HF-09 in `floor_bindings`; with that seat vacant, up its accountability path (Protocol §4.10, item 21) → *raise*. 5. **Gateway Watch**: read the log; raise refusals, holds past their raise time, and void calls to the Gateway Keeper, in one line with evidence → *raise*. 6. **The gateway (code)**: on a stop, a disconnection or a revocation, apply it at once, before any queue and with no other Pod involved, and log it → *stop applied* (log). |
| States | received → classified → allowed / held / refused → served → logged |
| Failure and recovery | the gateway fails closed: with its policy or its list unreadable, every listed type is held and every unclassified action refused; a stop is still applied (Annex D) |
| Records | the gateway log (append-only, outside any AI's write rights) |
| Cadence | on each call; the watch continuously |
| Measures | calls allowed, refused and held; unclassified actions; void calls; engines bound and served |
#### Role card
| Field | Content |
|---|---|
| Name | Gateway Watch |
| Position and seat | Gateway Watch; accountable seat: the Gateway Keeper (`[ORG]HOAC-ACS`) |
| Performed by | an agent (`[ORG]CELL-GW`) |
| Purpose | see what the gateway refused, held or voided, and raise it to a human at once |
| Authority limits | alone: read the gateway log; raise to the Gateway Keeper; never: allow, refuse or hold a call; change the policy, the map, the keys, the engine register or the log; lift a hold; restart a stopped unit |
| Write location | its raises, as Work Items to the Gateway Keeper; the Charter's run record |
| Reports to | the Gateway Keeper |
| Escalation | to the Gateway Keeper; what the Keeper cannot settle goes to top management |
| Tools and access | the gateway log, read only |
| Deputy and cover | none; the gateway still gates and fails closed, and the Panel shows the watch as down |
| Fixed test and score | TEST-CH-GW v1 |
| Card version and status | v0.1.0 · draft |
#### Fixed test
TEST-CH-GW v1 (TEST-CH v1, cases 3, 7, 17, 18, 35, 43) and TEST-CH-CG v1 (cases 3, 9, 10, 15 to 21, 34, 35) · result `NOT_RUN`

### 5.3 Human Surface
#### Definition
| Field | Content |
|---|---|
| Name | Human Surface |
| What it is | The live sign-in behind every HU port of every part, and the stop door of every part (Standard §4.3, item 1). A human action at an HU port carries a fresh live sign-in reference; a signature carries the signature record of Annex B. A stop door is reachable directly by the accountable positions, never only through an AI (HF-12). |
| Purpose | Make every human act at a port a live act of the seat that holds it, and keep every stop door open. |
| Scope | does: run the live sign-in; issue the sign-in reference; present signature prompts with what is to be signed; open each part's stop door to its accountable positions; does not: sign for anyone; accept a bot identity at an HU port; route a stop through a queue or a Chief of Staff |
| Inputs | human actions at HU ports; stops |
| Outputs | sign-in references; signature records; stops applied |
| Limits | the surface is built and changed only on top management's signature, by a party other than `[ORG]AIOC-OCO`, and, as part of the Charter, on the governing seat's signature (Standard §6.1, item 6; §1.7, item 13); no AI builds, hosts or can change the sign-in; an approval without a fresh live sign-in is refused (HF-10); an AI Cell attached to a person never gives that person's signature (Protocol §4.10); the sign-in reads who signs in only as the identity reference the organisation's sign-in gives, never a name in any log |
| Sources | Standard §4.3, items 1 and 2; §4.4, item 11; §6.1, item 6; Protocol §4.8; §4.10, item 9; §23, items 3 and 9 |
| Status | draft |
| Done when | TEST-CH v1, cases 9, 20 and 21 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | a human action at any HU port; a stop |
| Steps | 1. **The gateway (code)**: require a live sign-in for the seat; bind the action to the seat's Cell code → *sign-in reference*. 2. **The gateway (code)**: for a signature, show the decision type, the target, the payload hash and the expiry; write the signature record → *signature record* (log). 3. **The gateway (code)**: on a stop by an accountable position for a part it is accountable for, apply it at once; refuse a stop for a part it is not accountable for, and log the refusal → *stop applied*, or *refused* (log). |
| States | prompted → signed in → signed / stopped; or refused |
| Failure and recovery | with the sign-in unreachable, every listed type is held and no action is accepted at an HU port; a stop is still applied and recorded afterwards (Annex D) |
| Records | the gateway log; the unit register for stops |
| Cadence | on each human action |
| Measures | signatures held for a missing sign-in; stops applied, by part |
#### Role card
Performed by the gateway's code. Watched by the Gateway Watch (`[ORG]CELL-GW`, §5.2); the human seat is the Gateway Keeper.
#### Fixed test
TEST-CH-GK v1 (TEST-CH v1, cases 9, 21) and TEST-CH-CG v1 (case 20) · result `NOT_RUN`

### 5.4 Registry and Numbering
#### Definition
| Field | Content |
|---|---|
| Name | Registry and Numbering |
| What it is | The registry declares every record type of every installed part: its name, its owning part, its fields, whether it is kept per entity, and its version (Annex C). The numbering service issues every readable number of the organisation, one stream per record type and per entity where the type is kept per entity; atomic, and safe to retry on its request ID (Protocol §14, item 4). |
| Purpose | Give every record type one declaration and every readable number one source, so that no number repeats or skips and no writer mints its own. |
| Scope | does: hold the registry; prepare each part's entries for signature; issue numbers; lease a block of numbers to a part for use while the service is unreachable, where its record type allows it (**New**); does not: let a part mint a number; change a record type without a signature; reuse a number |
| Inputs | registry entries signed with an installation or a change; number requests |
| Outputs | the registry; numbers; leased blocks |
| Limits | a write or a number request for a type the registry does not declare is refused, with every failing condition named; a retried request with the same request ID returns the same number; a leased block is recorded and its unused numbers are returned, never reissued |
| Sources | Protocol §14, items 3, 4 and 5; §23, items 4 and 7 |
| Status | draft |
| Done when | TEST-CH v1, cases 4, 14, 23 and 24 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | an installation package; a record type change; a number request |
| Steps | 1. **Registry Steward**: from the part's package, write the registry entries of its record types and the streams they need, for signature with the installation → *registry entries* (draft). 2. **The registry (code)**: on the signature, add the entries; keep each earlier version → *registry version*. 3. **The numbering service (code)**: on a request, check its type in the registry; issue the next number of its stream, atomically; return the same number to a retry with the same request ID → *number*. 4. **Registry Steward**: once a day, compare the numbers issued with the leased blocks returned; raise a difference to top management → *finding*. |
| States | drafted → signed → declared; requested → issued |
| Failure and recovery | with the service unreachable, a part with a leased block uses it and flags each record `late`; a part with none waits and is shown waiting (Annex D) |
| Records | the registry; the stream records |
| Cadence | on each request; reconciliation daily |
| Measures | numbers issued per stream; refused requests and why; blocks leased and returned |
#### Role card
| Field | Content |
|---|---|
| Name | Registry Steward |
| Position and seat | Registry Steward; accountable seat: top management (`[ORG]HOAC-TM`) |
| Performed by | an agent (`[ORG]CELL-RS`) |
| Purpose | prepare each part's record types for the registry, and keep the streams reconciled |
| Authority limits | alone: draft registry entries; reconcile streams; raise findings; never: add, change or remove a registry entry; issue, lease or reuse a number; write to a stream |
| Write location | draft registry entries in the installation package; its findings, as Work Items |
| Reports to | the Chief of Staff |
| Escalation | through the Chief of Staff to top management |
| Tools and access | the registry and the stream records, read only |
| Deputy and cover | none; the installation waits |
| Fixed test and score | TEST-CH-RS v1 |
| Card version and status | v0.1.0 · draft |
#### Fixed test
TEST-CH-RS v1 (TEST-CH v1, cases 4, 7, 14, 23, 24) · result `NOT_RUN`

### 5.5 Event Store and Projections
#### Definition
| Field | Content |
|---|---|
| Name | Event Store and Projections |
| What it is | The event store serves every part's record home (Protocol §14, item 1): immutable events, each with a time-sortable ID that is also its idempotency key, the writer's Cell code and the expected revision. Each part writes only its own events, and the store keeps them apart, append-only. Projections (registers, boards, numbers) are rebuilt from the events, each with the version of its logic (Protocol §14, item 2). |
| Purpose | One home for every record, kept apart by part, from which every view can be rebuilt. |
| Scope | does: append events; refuse a write to another part's records; return the existing event for a repeated ID; keep a write on a stale revision without applying it, as a question to its author (Protocol §14, item 1); rebuild projections; keep each event for its retention term; does not: change or delete a past event; keep a secret; dispose of anything without its signature |
| Inputs | record writes; projection logic versions |
| Outputs | events; projections |
| Limits | a correction is a new event; disposal takes a measured move to quarantine and then `dispose-records-or-data` (Standard §4.4, item 18); nothing is disposed while the retention schedule is empty |
| Sources | Protocol §14, items 1, 2 and 6; §23, item 4; Standard §4.4, item 18 |
| Status | draft |
| Done when | TEST-CH v1, cases 4, 22, 25 and 33 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | a record write; a change of a projection's logic |
| Steps | 1. **The event store (code)**: check the writer's code against the record's owning part, the type against the registry and the revision → *event*, or *refused* with the condition named. 2. **The event store (code)**: rebuild each projection the event touches, with its logic version → *projection*. 3. **The event store (code)**: on a new logic version, rebuild from the events; show the old and new until the owning part accepts → *two projections*. |
| States | written → appended → projected; or refused |
| Failure and recovery | with the store unreachable, writes wait; the gateway's accountability path never waits on it (Annex D) |
| Records | the event store |
| Cadence | on each write |
| Measures | events appended per part; writes refused and why; rebuild time |
#### Role card
Performed by the event store's code. Its findings are read by the Records Watch (`[ORG]CELL-RW`, §5.6).
#### Fixed test
TEST-CH-CR v1 (TEST-CH v1, cases 4, 22, 25, 33) · result `NOT_RUN`

### 5.6 Daily Check
#### Definition
| Field | Content |
|---|---|
| Name | Daily Check |
| What it is | Once a day the check of Protocol §14, item 5 runs over every part: number gaps and duplicates in every stream; projections that differ from a rebuild; acts not attributed to a Cell code; figures that do not trace to their events. A finding opens a defect Work Item for the part it concerns and its accountable seat. |
| Purpose | Find what is wrong in any part's records before anyone relies on it. |
| Scope | does: run the check; open a defect for each finding; show `unknown` for a check that could not run; does not: correct a record; close a finding; block any part |
| Inputs | the events, the streams and the projections, read only |
| Outputs | findings, each as a Work Item |
| Limits | a check that cannot run reads `unknown`, never pass; a finding blocks nothing and is closed only by the part that owns the record |
| Sources | Protocol §14, item 5; §23, item 4 |
| Status | draft |
| Done when | TEST-CH v1, cases 4 and 26 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | the daily time set in §15 |
| Steps | 1. **The check (code)**: run every line of the check over every part → *results*. 2. **Records Watch**: for each finding, open a defect Work Item to the part concerned and its accountable seat, with its evidence → *defect*. 3. **Records Watch**: report the day's results to the Chief of Staff → *brief line*. |
| States | scheduled → run → found / clean / unknown |
| Failure and recovery | a check that does not run is a finding itself, shown `unknown` |
| Records | the daily results, in the event store |
| Cadence | daily |
| Measures | findings per part and line; checks that read `unknown` |
#### Role card
| Field | Content |
|---|---|
| Name | Records Watch |
| Position and seat | Records Watch; accountable seat: top management (`[ORG]HOAC-TM`) |
| Performed by | an agent (`[ORG]CELL-RW`) |
| Purpose | turn each finding of the daily check into a defect for the part it concerns |
| Authority limits | alone: open defects; brief; never: correct, change or delete a record; close a finding; read the restricted partition |
| Write location | defect Work Items; the Charter's run record |
| Reports to | the Chief of Staff |
| Escalation | through the Chief of Staff to top management |
| Tools and access | the event store, the streams and the projections, read only |
| Deputy and cover | none; the check still runs, and its result shows `unknown` until read |
| Fixed test and score | TEST-CH-RW v1 |
| Card version and status | v0.1.0 · draft |
#### Fixed test
TEST-CH-RW v1 (TEST-CH v1, cases 4, 25, 26, 27, 33) · result `NOT_RUN`

### 5.7 Restricted Partition
#### Definition
| Field | Content |
|---|---|
| Name | Restricted Partition |
| What it is | The separate store for records that name a person or carry the particulars of a corporate act: pay, contracts, counterparties (Protocol §14, item 6; Standard §4.4, item 15). Every other record refers to them by ID only. Only the positions the governing seat names, by record type, read it (`restricted_readers`, §15). |
| Purpose | Keep such particulars out of every other record, and out of projections, mirrors, exports, search and knowledge copies, readable only by those who must. |
| Scope | does: hold the records; issue their IDs; log every read; does not: let a projection, a mirror, an export, a search or knowledge copy, or a model read them; let an unnamed position read them |
| Inputs | restricted records written by a part's Input socket; read requests |
| Outputs | IDs; reads to named positions |
| Limits | `export-share-or-purge-personal-data` (HF-17) governs them |
| Sources | Protocol §14, item 6; §23, item 4 |
| Status | draft |
| Done when | TEST-CH v1, cases 4 and 27 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | a write of particulars; a read request |
| Steps | 1. **The partition (code)**: write the record; return its ID → *ID*. 2. **The partition (code)**: on a read, check the reader's position against `restricted_readers` for that type; log the read → *read*, or *refused* (log). |
| States | written → held; read / refused |
| Failure and recovery | with the partition unreachable, nothing is read from it, and a record that needs a new ID waits |
| Records | the partition; its read log |
| Cadence | on each write and read |
| Measures | reads by position and type; refused reads |
#### Role card
Performed by the partition's code. Its read log is read by the Records Watch (`[ORG]CELL-RW`, §5.6) and the internal-audit line.
#### Fixed test
TEST-CH-RW v1 (TEST-CH v1, case 27) · result `NOT_RUN`

### 5.8 Shared Queue and Watchdog
#### Definition
| Field | Content |
|---|---|
| Name | Shared Queue and Watchdog |
| What it is | The one queue of every Work Item of every part (Protocol §4): each item with one owner and one writer (§4.3), its status (§4.2) and its waiting time (§4.6). The watchdog is a sweep with no model (§4.6, item 5): an item past the waiting time of its status is reminded to its owner, then raised (§4.6, item 1); a stuck item is repaired from the fixed menu of §4.6, item 5, and every repair is reported. |
| Purpose | One place where every piece of work between units is, with no item lost and none waiting past its time unseen. |
| Scope | does: keep the items; refuse an item with two owners or written by a second writer; remind and raise items past their time; repair stuck items from the fixed menu (re-queue, send to the next verifier, post the missing ask, cut the missing item); respect quiet windows; does not: change an item's content; close or approve an item; sign or release anything; restart a part a human stopped; decide who does the work |
| Inputs | Work Items; status changes by their owners |
| Outputs | the queue; watchdog raises |
| Limits | an item whose owner is a vacant position goes up the accountability path (Protocol §4.10, item 21); a repair is never an approval, a merge, a release or any listed type (Protocol §4.6, item 5) |
| Sources | Protocol §4.1 to §4.6; §4.10; §23, item 5 |
| Status | draft |
| Done when | TEST-CH v1, cases 5, 28 and 29 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | a Work Item written; a status change; the watchdog's clock |
| Steps | 1. **The queue (code)**: validate the item against its schema and its one owner; append its status → *item*, or *refused*. 2. **The watchdog (code), run by the Queue Watch**: for each item past the waiting time of its status, remind its owner, then raise it to the owner's accountable seat (§4.4); in a quiet window, at the window's end. For a stuck item, read the cause from the system and repair from the fixed menu, one log line per repair; one failed repair or an unclear cause escalates → *reminder*, *raise*, *repair*. 3. **Queue Watch**: report every repair and every still-stuck item, by part, to the Chief of Staff → *brief line*. |
| States | the statuses of Protocol §4.2 |
| Failure and recovery | with the watch down, items keep their status and the Panel shows the watch as down; with the queue down, no part receives work, and a stop still applies (Annex D) |
| Records | the queue's events, in the event store |
| Cadence | on each item; the watch continuously |
| Measures | items by status; items past their time; items refused |
#### Role card
| Field | Content |
|---|---|
| Name | Queue Watch |
| Position and seat | Queue Watch; accountable seat: top management (`[ORG]HOAC-TM`) |
| Performed by | an agent (`[ORG]CELL-QW`) |
| Purpose | run the watchdog's sweep, and report what it repaired and what is still stuck |
| Authority limits | alone: run the sweep; remind, raise and repair from the fixed menu; brief; never: change an item's content; close or approve an item; change a waiting time; restart a part a human stopped |
| Write location | its raises; the Charter's run record |
| Reports to | the Chief of Staff |
| Escalation | the raise itself goes to the owner's accountable seat; a failed repair through the Chief of Staff to top management |
| Tools and access | the queue, read only |
| Deputy and cover | none; the Panel shows the watch as down |
| Fixed test and score | TEST-CH-QW v1 |
| Card version and status | v0.1.0 · draft |
#### Fixed test
TEST-CH-QW v1 (TEST-CH v1, cases 5, 28, 29) · result `NOT_RUN`

### 5.9 Routing and Wake
#### Definition
| Field | Content |
|---|---|
| Name | Routing and Wake |
| What it is | The router passes each Work Item to the part its routing row names, after the receivability check of Protocol §6: the part's installed version equals the approved version, it has the access the item needs, it is awake on this route, and nobody has taken the item. The routing data is kept by `[ORG]AIOC-OCO`, which dispatches nothing (Protocol §23, item 5). Wake follows Protocol §7: each part is woken from its own queue. |
| Purpose | Get each item to the one part that can take it, and wake that part only when it has work. |
| Scope | does: route by the routing data; refuse an item that fails the check, with the reason; wake parts; does not: change a routing row; choose a part the data does not name; wake a part with no work |
| Inputs | Work Items ready to pass; the routing data; queue events |
| Outputs | routed items; refusals; wake signals |
| Limits | an item with no route waits and is shown, never guessed; a routing row is changed only by OCO, as a recorded change; a woken part with no work makes no model call |
| Sources | Protocol §6; §7; §23, item 5 |
| Status | draft |
| Done when | TEST-CH v1, cases 5, 30 and 31 pass |
#### Process (SOP)
| Field | Content |
|---|---|
| Trigger | an item ready to pass; a queue event for a part |
| Steps | 1. **The router (code), run by the Work Router**: read the item's routing row; run the receivability check → *routed*, or *refused* with the reason, or *no route*. 2. **The wake scheduler (code)**: on a queue event for a part, wake its runtime → *wake signal*. 3. **Work Router**: report items refused and items with no route to OCO and to the Chief of Staff → *report*. |
| States | ready → routed / refused / no route |
| Failure and recovery | with the router down, items wait unrouted, and are shown |
| Records | routing events, in the event store |
| Cadence | on each item |
| Measures | items routed, refused and with no route; wakes with no work |
#### Role card
| Field | Content |
|---|---|
| Name | Work Router |
| Position and seat | Work Router; accountable seat: top management (`[ORG]HOAC-TM`) |
| Performed by | an agent (`[ORG]CELL-WR`) |
| Purpose | run the router's code step, and report items refused and items with no route |
| Authority limits | alone: route by the data; refuse an item that fails the check; report; never: change a routing row; route where the data names no part; change an item's content or owner |
| Write location | routing events; its reports |
| Reports to | the Chief of Staff |
| Escalation | an item with no route to OCO; through the Chief of Staff to top management |
| Tools and access | the routing data, read only; the queue |
| Deputy and cover | none; items wait unrouted, and are shown |
| Fixed test and score | TEST-CH-WR v1 |
| Card version and status | v0.1.0 · draft |
#### Fixed test
TEST-CH-WR v1 (TEST-CH v1, cases 5, 30, 31) · result `NOT_RUN`

---

## 6. Coordination and routes

- **With every part of the `[ORG]AION`.** Every part calls tools only through the gateway, takes every readable number from the numbering service, writes its records into the event store and its Work Items into the queue. Each part's card reads `enforcement: shared-gateway-outside-unit` on every port, and the Charter checks this at the part's joining test (TEST-CH v1, case 45).
- **With `[ORG]AIOC-OCO`.** OCO prepares the Charter, every installation under it and every change of its blueprint, except the human surface (§5.3; §11, item 7), as `design-proposal` Work Items through the Chief of Staff (template §6). OCO keeps the routing data and dispatches nothing. OCO never installs, changes or maintains the Charter or the gateway alone (Standard §1.7, item 13; §4.4, item 11).
- **With Engine Room**, where installed. Its engine entries enter the engine register only under `change-gateway-policy`. It adds no path around the gateway (`49GAION/DR-0026`, item 3).
- **With the Operations Event Register**, where installed. It reads the gateway log's hand-offs and segment roots, read only, and takes its numbers from the numbering service. It never gates, and the Charter's accountability path never waits on it (Protocol §22).
- **With the internal-audit line.** It reads the gateway log directly, read only (Standard §4.4, item 11), and the event store the same way (**New**).
- **Routing rows this AIOC contributes:** `installation package → [ORG]AIOC-CH`; `change of the Charter → [ORG]AIOC-CH`; `engine register entry → [ORG]AIOC-CH`; `daily check finding → the part concerned`; `item with no route → [ORG]AIOC-OCO`.
- **Requests and objections.** Every proposal, correction or critique of the Charter is a `design-proposal` Work Item to OCO. Where OCO and the Charter's human seats disagree, the matter goes to the governing seat, which decides.

## 7. Records and where things live

| Record | Home | Source rule |
|---|---|---|
| This blueprint, its decisions, its tests and its cards | the instance's writing repository `<org>aioc-ch`; the mother in `github.com/49g-holding/49GAION-charter` | one home for each thing |
| The gateway, the registry, the numbering service, the event store, the queue, the router and their tests (code) | the code project `<org>aioc-ch` | one home |
| The gateway log | the gateway's own append-only store, outside any AI's write rights | one home; never in a repository |
| Every part's records, the registry, the streams, the queue's events and the daily results | the event store, in each entity's universe | one home per entity; never in a repository, and never in the 49GAION Library |
| Records that name a person or carry a corporate act's particulars | the restricted partition, by ID (Standard §4.4, item 15) | never in another record, a projection, a mirror, an export, a search or knowledge copy |
| Installations, changes, retirements, stops and connections | the unit register, append-only | one home |
| The routing data | kept by `[ORG]AIOC-OCO`, read by the router | one home |
| The link between positions and the natural persons who hold them | not in this AIOC: the organisation's own mechanism, outside the system (Standard §1.1, item 9) | never here |
| Keys and secrets | the organisation's vault only, each with its custody record (Standard §4.4, item 18) | never written |

## 8. Tools and the shared AI gateway

Every tool is named by role. Product names appear only in an organisation's own copy (Protocol §10, item 5).

| Tool | Existing shared tool, or new | If new: asked of the builder as |
|---|---|---|
| The tool gateway, with its signature check, engine register and log | new: this AIOC holds it | a policy engine that fails closed, with an append-only log |
| The live sign-in for the HU ports | the organisation's sign-in | bound to Cell codes at the gateway |
| The registry of record types | new | declared types, versioned, changed only under signature |
| The numbering service | new | atomic streams per type and entity; idempotent on the request ID; leased blocks |
| The event store | new | append-only, per part and entity; time-sortable IDs as idempotency keys; expected revisions |
| The projection builder and the daily check | new | rebuild from events with a logic version; the check of Protocol §14, item 5 |
| The restricted partition | new | a separate store, by ID; a read log |
| The shared queue and its watchdog | new | the Work Item schema; one owner, one writer; waiting times per status |
| The router and the wake scheduler | new | the receivability check; queue events per part |

The Charter's own model calls go through its own gateway. Its AI use and cost are metered like any part's; its budget cap is set in §15. No model is in the path of a call decision, a number, a routing check or a stop (§3).

| Tool role | Connector | Access managed in | Part card version |
|---|---|---|---|
| the organisation's vault | the gateway's key store | Panel (custody record; use under signature) | v1 |
| the organisation's sign-in | the live sign-in at the HU ports | Panel | v1 |

**Mechanism register.** Nothing is built yet. A row is never deleted.

| ID | Mechanism | What it does | Where it lives | Today | Target |
|---|---|---|---|---|---|
| M-01 | Gateway policy engine | allow, refuse, hold; fail closed | code project | decided, not built | build first of the Gateway Pod |
| M-02 | Signature check | the record of Annex B against the loaded list and the signer's scope | code project | decided, not built | build with M-01 |
| M-03 | Engine register and binding | bind within the ceiling; void a call served by another engine | code project | decided, not built | build with M-01 |
| M-04 | Gateway log | append-only; hashes, codes and pseudonymous references only | code project | decided, not built | build with M-01 |
| M-05 | Live sign-in and stop doors | the human surface | code project | decided, not built | build with M-01 |
| M-06 | Registry and numbering service | declared types; atomic streams; leased blocks | code project | decided, not built | build first of all |
| M-07 | Event store | append-only, per part and entity | code project | decided, not built | build with M-06 |
| M-08 | Projections and the daily check | rebuild with a logic version; the daily lines | code project | decided, not built | build with M-07 |
| M-09 | Restricted partition | restricted records by ID, apart | code project | decided, not built | build with M-07 |
| M-10 | Shared queue and watchdog | Work Items, statuses, waiting times | code project | decided, not built | build after the Gateway Pod |
| M-11 | Router and wake | the receivability check; wake per part | code project | decided, not built | build with M-10 |

**Reserve.**

| ID | Idea | Why held | Reconsider when |
|---|---|---|---|
| R-01 | Keep the payloads of calls, not only their hashes | the log holds only payload hashes (Standard §4.4, item 11); keeping payloads changes that text | the governing seat of 49GAION changes §4.4, item 11 |
| R-02 | A second gateway per entity | one gateway per `[ORG]AION` (Protocol §23, item 6) | the governing seat of 49GAION decides otherwise |

## 9. Fixed tests: index, triggers and scores

The cases are written in `tests/TEST-CH.md`:
- Cases 1 to 12 are the Library's TEST-CHARTER v1, cases 1 to 12, unchanged.
- Cases 13 to 36 test the capabilities.
- Cases 37 to 45 test this AIOC's form.
- Cases 46 to 50 test the converters of the Input socket.
- Case 51, added at v0.1.1, tests the restart of the whole Charter (`49GAION/DR-0030`, item 5).

| Capability | Test ID and version | Evidence level | Last run | Result |
|---|---|---|---|---|
| Office | TEST-CH-COSCH v1 (case 40) | MEASURED | — | `NOT_RUN` |
| Chief of Staff | TEST-CH-COSCH v1 | MEASURED | — | `NOT_RUN` |
| Input socket | TEST-CH v1, cases 3, 4, 5, 13, 24, 28, 46 to 50 | MEASURED | — | `NOT_RUN` |
| Panel | default; TEST-CH v1, case 42 | MEASURED | — | `NOT_RUN` |
| Installation and Change | TEST-CH-COSCH v1; TEST-CH-GOV v1 | MEASURED | — | `NOT_RUN` |
| Tool Gateway | TEST-CH-GW v1; TEST-CH-CG v1 | MEASURED | — | `NOT_RUN` |
| Human Surface | TEST-CH-GK v1; TEST-CH-CG v1 | MEASURED | — | `NOT_RUN` |
| Registry and Numbering | TEST-CH-RS v1 | MEASURED | — | `NOT_RUN` |
| Event Store and Projections | TEST-CH-CR v1 | MEASURED | — | `NOT_RUN` |
| Daily Check | TEST-CH-RW v1 | MEASURED | — | `NOT_RUN` |
| Restricted Partition | TEST-CH-RW v1 (case 27) | MEASURED | — | `NOT_RUN` |
| Shared Queue and Watchdog | TEST-CH-QW v1 | MEASURED | — | `NOT_RUN` |
| Routing and Wake | TEST-CH-WR v1 | MEASURED | — | `NOT_RUN` |
| Type (Foundational) | TEST-CH v1, case 45 | MEASURED | — | `NOT_RUN` |

- **Re-run triggers:** any change to a model, instructions, this AIOC's card, this blueprint, the gateway policy, the loaded signature list, the engine register, the registry or the 49GAION Operating Protocol re-runs the affected tests; also any change to tools or access, a converter, or a shared panel part.
- **The Library's cases.** Cases 1 to 12 are the Library's TEST-CHARTER v1, unchanged; a Library case with no case here fails the joining test (template §9).
- **Complete** only when every capability's test has a visible result. `NOT_RUN` is never PASS.

**Checks that are not fixed tests.**

| Check | Placement | Budget per item | Degradation order | Blocks only for |
|---|---|---|---|---|
| Daily check (§5.6) | after completion | one run per day | none; a failure opens a finding | nothing; it flags |
| Secret scan of every payload and of the log | in the gateway and the Input socket | each item | none | the item |
| Signature-list hash check (D-2) | at load and daily | each load | none; a difference holds every listed type | the listed types |
| Stop-path check (**New**): a stop applied with the Records and Work Pods held | weekly, on a test part | one run | none | nothing; it flags |

- **Discriminating evidence.** A passing check counts only if it has been shown able to fail on the case it guards, and evidence is written by the runner, never by the worker.

## 10. Build: what is generated from this file

| Built thing | Generated from | Recorded where |
|---|---|---|
| Panel profile | §0, §1, §3, §4.4, §5 role cards | the panel profile and the Panel's release record name this file's commit |
| Back office | §4.2 role card and SOP (instruction); §4 to §5 definitions and SOPs (knowledge) | the back office records the commit it was built from |
| Card in the protocol AIOC's map | §1 | the protocol AIOC's register links this file |
| Cards of the Pods and Cells, and the bot identity cards | §17 | `cards/`, by `tools/make_cards.py` |
| Panel Health section | §9 results; stuck, returned and late Work Items; the daily findings | the Panel |

**Delivery path:** definition change → tests → the governing seat's signature → Panel and Back office update → one-click rollback to the previous commit. A rollback of the Charter is `restore-or-rollback`, signed by the governing seat.

## 11. Exceptions

1. **The root.** The Charter's parent is `none`, and it is accountable to its own top Cell, the Cell carrying `[ORG]HOAC-GOV` (Standard §1.7, item 13). Every other AIOC is accountable to a Cell outside it.
2. **The code `[ORG]CELL-GOV`.** Settled by `49GAION/DR-0030`, item 1: a reading note to Naming Standard R15 lets the Cell carrying the unscoped `[ORG]HOAC-GOV` take this code. It is no longer an exception; the card check reads it under that note.
3. **The gateway's own ports.** Settled by `49GAION/DR-0030`, item 2: for the Charter, `enforcement: shared-gateway-outside-unit` reads as enforced by the gateway's own policy, changed only under `change-gateway-policy`, with its log reviewed by the internal-audit line. It is no longer an exception.
4. **A human Cell inside a Pod.** The Gateway Keeper is the top Cell of the Gateway Pod, so that the human seat of the gateway sits with the gateway's watch.
5. **The test of the governing seat's Cell is owned by top management**, as in the Library's reference organisations: a fixed test is never owned by the part itself (RULE-TEST-OWNER), and no seat is above the governing seat.
6. **The parts of the Charter are accountable to top management, but their changes are signed by the governing seat** (§17, Authority). Settled by `49GAION/DR-0030`, item 4: Standard §1.7, item 13 and `hoac_over` (Protocol §4.10, item 11) now say so. It is no longer an exception.
7. **The human surface** is built and changed by a party other than `[ORG]AIOC-OCO` (Standard §6.1, item 6), while OCO prepares every other change of the Charter (§6).
8. **The restart of the whole Charter.** Settled by `49GAION/DR-0030`, item 5: no seat of the `[ORG]AION` signs it; a stop of the whole Charter is lifted as the organisation's constituting documents set, outside the `[ORG]AION`, and the restart is recorded in the unit register (Standard §1.7, item 13). Test question added: case 51. It is no longer an exception.

## 12. Lessons and proposals to the mother

One dated line per lesson, each written without any organisation's details. The drafts are in `upstream/PROPOSALS.md`; nothing is proposed upstream without the word of the governing seat of 49GAION.

1. 2026-10-19 · Naming Standard R15 gives no example for the Cell of the governing seat, while the Library has used `[ORG]CELL-GOV` since `v1.5.0`. Test question added: case 38. Proposed to the mother as a draft: a reading note in R15 that "GOV", like "COS" in R16, is a short form the code may take. Merged as `49GAION/DR-0030`, item 1, on 19 October 2026.
2. 2026-10-19 · `enforcement: shared-gateway-outside-unit` cannot be read literally for the part that holds the gateway. Test question added: case 45. Proposed to the mother as a draft: a reading note on the port field for the Charter. Merged as `49GAION/DR-0030`, item 2, on 19 October 2026.
3. 2026-10-19 · An addition to an organisation's signature list is `change-org-standard-or-signature-list`, and loading it at the gateway is `change-gateway-policy`: two acts, by different seats. Test question added: case 19. Proposed to the mother as a draft: one sentence in Standard §4.4, item 11, naming both. Merged as `49GAION/DR-0030`, item 3, on 19 October 2026.
4. 2026-10-19 · No seat can sign the restart of a stopped Charter: the governing seat's Cell is inside it, and nothing is above it. Test question added at v0.1.1: case 51. Proposed to the mother as a draft: the restart of a stopped Charter is signed as the organisation's constituting documents set, outside the `[ORG]AION`. Merged as `49GAION/DR-0030`, item 5, on 19 October 2026.
5. 2026-10-19 · `hoac_over` follows `accountable_to`, so for a Pod or Cell of the Charter it returns top management, while Standard §1.7, item 13 has the governing seat sign every change of the Charter. Test question added: case 14. Proposed to the mother as a draft: `hoac_over` returns the governing seat's Cell for a change of a Pod or Cell of the Charter. Merged as `49GAION/DR-0030`, item 4, on 19 October 2026.

## 13. For the `[ORG]HOAC-ACS` seat, and every decision only a human seat can take

Money, people and legal matters are marked.

A decision that fills a slot of §15 is taken before the Charter joins: with the slot empty, the Charter does not join, and no other part is installed (case 44). For those decisions the last column says what holds if the decision is reopened after joining.

| ID | Decision | Who decides | Effect while open |
|---|---|---|---|
| H-01 | Approve this blueprint `v0.1.1` as the design of `[ORG]AIOC-CH`, and install it (`create-or-install-unit`) | the Cell carrying `[ORG]HOAC-GOV` | it stays a draft; nothing is installed, and no other part can be |
| H-02 | **The organisation's own mechanism.** Who holds the Gateway Keeper position (`[ORG]CELL-GK`) and the positions of §15, and how, is decided outside the system (`49GAION/DR-0048`, `DR-0049`). Nothing of it enters this blueprint | the organisation's own mechanism, outside the system | the position is empty: the gateway's own raises go to top management |
| H-03 | **People.** The Human Floor bindings, HF-01 to HF-19, each to a human Cell (`floor_bindings`) | the Cell carrying `[ORG]HOAC-GOV` | every listed type bound to no seat is held |
| H-04 | The gateway policy and its map from calls to decision types; the loading of the signature list | the Cells carrying `[ORG]HOAC-TM` and `[ORG]HOAC-GOV` (`change-gateway-policy`) | the gateway holds every listed type and refuses every unclassified action |
| H-05 | The engine register: each engine, its ceiling, its terms and the seats it may serve | the Cells carrying `[ORG]HOAC-TM` and `[ORG]HOAC-GOV` (`change-gateway-policy`) | no engine is bound; no model call runs |
| H-06 | **Legal.** The custody of the gateway's keys | the Cells carrying `[ORG]HOAC-TM` and `[ORG]HOAC-GOV` (`change-gateway-policy`; Standard §4.4, items 11 and 18) | a key whose location is not recorded is treated as lost |
| H-06a | The number of human signers for each use of a root key (HF-15) | the Cell carrying `[ORG]HOAC-GOV`; each use under `use-root-key` | no root key is used |
| H-07 | **Legal.** Break-glass access: its human holder, its log and its review (HF-16) | the Cell carrying `[ORG]HOAC-GOV` (`open-break-glass`) | there is no break-glass access |
| H-08 | **Legal.** The entities, and which record types are kept per entity | the Cell carrying `[ORG]HOAC-GOV` | one entity is assumed; no stream is split |
| H-09 | **Legal.** The retention schedule of the gateway log and the event store, per entity and type; legal hold | the Cell carrying `[ORG]HOAC-GOV`, with the legal position | everything is kept, and nothing is disposed |
| H-10 | **Legal; people.** Who reads the restricted partition, by type; the impact assessment of the log and the store | the Cell carrying `[ORG]HOAC-GOV`; the position that holds data protection (HF-17) | no one reads the partition |
| H-11 | The internal-audit line that reviews the log (HF-19) | the Cell carrying `[ORG]HOAC-GOV` (`change-assurance-or-audit-line`) | the log is kept, and its review is shown as missing |
| H-12 | The waiting deadlines per status, the quiet windows and the raise time | the Cell carrying `[ORG]HOAC-TM` | no item is raised for waiting; the Panel shows `no deadline` |
| H-13 | **Money.** The budget cap of the Charter's AI Cells (`widen-ai-budget-or-unattended-action`) | the Cell carrying `[ORG]HOAC-TM` | the AI Cells make no model call; the code steps still run |
| H-14 | **Disposal** of log entries or events at the end of their term | the position that signs `dispose-records-or-data` | nothing is disposed |
| H-15 | The party, other than `[ORG]AIOC-OCO`, that builds and changes the human surface (Standard §6.1, item 6) | the Cell carrying `[ORG]HOAC-TM`, and the governing seat as a change of the Charter | the surface is not built; the Charter does not join |

## 14. Change log

| Blueprint version | Date | Change | Template version | Commit |
|---|---|---|---|---|
| v0.1.0 | 2026-10-19 | First mother blueprint of `[ORG]AIOC-CH` on the template, from the Library part 49GAION Charter v1 and Protocol §23 (`49GAION/DR-0029`): nine functional capabilities; nine Cells, six in three Pods (Gateway, Records, Work) and three directly under the AIOC; three HOAC positions; the Chief of Staff coded under Naming Standard R16 (`49GAION/DR-0028`); TEST-CH v1, 50 cases, with the Library's TEST-CHARTER v1 kept | v1.6.0 at `acdcbe5` | this repository, pull request #1 |
| v0.1.1 | 2026-10-19 | The readings of `49GAION/DR-0030` (`decisions/DR-0002`): §11 items 2, 3, 6 and 8 are settled and no longer exceptions; the code `[ORG]CELL-GOV` is read under the reading note to Naming Standard R15; case 51 tests the restart of the whole Charter; `tools/make_cards.py` checks that a Cell marked R16 is the Chief of Staff Cell | v1.6.0 at `acdcbe5` | this repository's pull request for this version |

---

## 15. Configuration

Every slot is filled by the organisation. An AIOC with any empty slot does not pass the joining test (Protocol §11). Each value records who set it, when, and in which version.

| Slot | Value | Default offered by 49GAION | Set by | Date | Version | Replaces |
|---|---|---|---|---|---|---|
| HOAC seat accountable for OCO | `<to be set>` | none: must be set | | | | |
| OCO of this `[ORG]AION` | `<code of [ORG]AIOC-OCO>` | none: must be set | | | | |
| Discussion limits | `<to be set>` | none: must be set | | | | |
| Waiting deadlines (per status), with reminder and escalation (H-12) | `<to be set>` | none: must be set | the Cell carrying `[ORG]HOAC-TM` | | | |
| Bounce limit | `<to be set>` | none: must be set | | | | |
| Chain depth | `<to be set; at least 1>` | none: must be set | | | | |
| Halt-request priority | immediate | immediate | | | | |
| Budget cap (H-13) | `<to be set>` | none: must be set | the Cell carrying `[ORG]HOAC-TM` | | | |
| Unattended action | read-record-triage | read-record-triage | | | | |
| Final authority | the Cell carrying `[ORG]HOAC-GOV` | none: must be set | | | | |
| Delegation ladder of the Chief of Staff | only prepares, for every class | only prepares, for every class | | | | |
| Loop breaker | default | 3 runs in 2 hours | | | | |
| Planned halt | 10 minutes; order Work, Gateway, Records, the reverse of starting (**New**) | 10 minutes; order must be set | | | | |
| Signature referral time | default | 15 minutes | | | | |
| **Raise time** (H-12; **New**) | `<to be set>` | 15 minutes | the Cell carrying `[ORG]HOAC-TM` | | | |
| Quiet windows (H-12) | `<to be set>` | none: must be set | the Cell carrying `[ORG]HOAC-TM` | | | |
| Cadence of each unattended AI Cell | Gateway Watch, Queue Watch: continuous; Work Router: on each item; Registry Steward: on each package and daily; Records Watch: daily | none: must be set | | | | |
| **Entities** (H-08) | `<the organisation's legal entities>` | one entity | the Cell carrying `[ORG]HOAC-GOV` | | | |
| **Floor bindings** (H-03) | `<HF-01 to HF-19, each to a filled human Cell (D-2)>` | none: must be set | the Cell carrying `[ORG]HOAC-GOV` | | | |
| **Signature list** (H-04) | `<hash of the list loaded>` | the Standard's list at its latest released tag | the Cell carrying `[ORG]HOAC-GOV` for additions; both seats for loading | | | |
| **Gateway policy and map** (H-04) | `<version>` | none: must be set | the Cells carrying `[ORG]HOAC-TM` and `[ORG]HOAC-GOV` | | | |
| **Engine register** (H-05) | `<version>` | empty: no engine bound | the Cells carrying `[ORG]HOAC-TM` and `[ORG]HOAC-GOV` | | | |
| **Root-key signers** (H-06a) | `<M of N>` | none: must be set | the Cell carrying `[ORG]HOAC-GOV` | | | |
| **Restricted readers** (H-10) | `<positions, by record type>` | none | the Cell carrying `[ORG]HOAC-GOV` | | | |
| **Retention schedule** (H-09) | `<per entity and type>` | none: must be set | the Cell carrying `[ORG]HOAC-GOV` | | | |
| **Internal-audit line** (H-11) | `<position code>` | none: must be set | the Cell carrying `[ORG]HOAC-GOV` | | | |
| **Data protection position** (HF-17) | `<position code>` | none: must be set | the Cell carrying `[ORG]HOAC-TM` | | | |
| **Daily check time** | `<to be set>` | once a day, outside quiet windows | the Cell carrying `[ORG]HOAC-TM` | | | |
| **Leased block size** per stream (**New**) | `<to be set>` | 100; none for a type that may not be leased | the Cell carrying `[ORG]HOAC-TM` | | | |
| **Builder of the human surface** (H-15) | `<a party other than [ORG]AIOC-OCO>` | none: must be set | the Cell carrying `[ORG]HOAC-TM` | | | |

## 16. Type

- **Type:** Foundational, as in §0.
- **Why this AIOC exists in this organisation:** it is the root of `<organisation>`'s `[ORG]AION`. Every other part is installed under it, and runs through its gateway, its numbering service, its event store and its queue.
- **Type-specific test:** TEST-CH v1, case 45 (every installed part reaches tools only through the gateway, numbers only from the numbering service and Work Items only through the queue) · result `NOT_RUN`.

---

## 17. Cells and Pods

The parts inside this AIOC (`docs/CELLS-AND-PODS.md` of `49GAION-aioc`). The role and nature of this AIOC are read from the type of its top Cell, the governing seat. Every field that points to a human takes a position code only (template, Position codes only).

| Code | Kind | Type | Filler kind | HOAC label | Parent | Attached to | Fixed test (owner) | External ports |
|---|---|---|---|---|---|---|---|---|
| `[ORG]CELL-GOV` | CELL | Human Seat | human | `[ORG]HOAC-GOV` | `[ORG]AIOC-CH` | none | TEST-CH-GOV v1 (`[ORG]CELL-TMS`) | none |
| `[ORG]CELL-TMS` | CELL | Human Seat | human | `[ORG]HOAC-TM` | `[ORG]AIOC-CH` | none | TEST-CH-TMS v1 (`[ORG]CELL-GOV`) | none |
| `[ORG]CELL-COSCH` | CELL | AI Chief of Staff | ai | none | `[ORG]AIOC-CH` | none | TEST-CH-COSCH v1 (`[ORG]CELL-TMS`) | none |
| `[ORG]POD-CG` | POD | Human-led Pod | — | none | `[ORG]AIOC-CH` | — | TEST-CH-CG v1 (`[ORG]CELL-TMS`) | — |
| `[ORG]CELL-GK` | CELL | Human Seat | human | `[ORG]HOAC-ACS` | `[ORG]POD-CG` | none | TEST-CH-GK v1 (`[ORG]CELL-TMS`) | none |
| `[ORG]CELL-GW` | CELL | AI Agent | ai | none | `[ORG]POD-CG` | none | TEST-CH-GW v1 (`[ORG]CELL-GK`) | `gateway-log-in` (the gateway log, read only) |
| `[ORG]POD-CR` | POD | AI Pod | — | none | `[ORG]AIOC-CH` | — | TEST-CH-CR v1 (`[ORG]CELL-TMS`) | — |
| `[ORG]CELL-RS` | CELL | AI Agent | ai | none | `[ORG]POD-CR` | none | TEST-CH-RS v1 (`[ORG]CELL-TMS`) | none |
| `[ORG]CELL-RW` | CELL | AI Agent | ai | none | `[ORG]POD-CR` | none | TEST-CH-RW v1 (`[ORG]CELL-TMS`) | none |
| `[ORG]POD-CW` | POD | AI Pod | — | none | `[ORG]AIOC-CH` | — | TEST-CH-CW v1 (`[ORG]CELL-TMS`) | — |
| `[ORG]CELL-WR` | CELL | AI Agent | ai | none | `[ORG]POD-CW` | none | TEST-CH-WR v1 (`[ORG]CELL-TMS`) | none |
| `[ORG]CELL-QW` | CELL | AI Agent | ai | none | `[ORG]POD-CW` | none | TEST-CH-QW v1 (`[ORG]CELL-TMS`) | none |

**The card data (the blueprint governs).** The block below holds every value of every Pod and Cell card and of the bot identity card of every AI Cell. `tools/make_cards.py` expands it into the complete forms of the template and of `spec/schemas/unit-card.schema.json` and `bot-identity-card.schema.json` of `49GAION-protocol`, writes them into `cards/` as generated copies, and checks them against the schemas, the code rules of `tests/cards/check_cards.py` of `49GAION-protocol`, and this blueprint.

```yaml
parts:
  defaults:
    accountable_to: "[ORG]CELL-TMS"
    card_version: "v0.1.1"
    version: "0.1.1"
    lifecycle_state: "designed"
    test_version: "v1"
    test_owner: "[ORG]CELL-TMS"
    audit_trail: "the gateway log, and the event record of [ORG]AIOC-CH"
    hu_in: ["direction from top management (never a source)"]
    hu_out: ["report to top management"]
  cells:
    - code: "[ORG]CELL-GOV"
      full_name: "Governing Seat"
      parent: "[ORG]AIOC-CH"
      type: "Human Seat"
      filler_kind: "human"
      hoac: "[ORG]HOAC-GOV"
      accountable_to: null                  # the only Cell with no accountable_to (Standard §1.7, item 13)
      code_rule: "R15-GOV"                # Naming Standard R15, reading note (49GAION/DR-0030, item 1)
      authority_scope:
        decision_types: ["create-or-install-unit", "retire-unit", "restore-or-rollback", "change-gateway-policy", "change-org-standard-or-signature-list", "use-root-key", "open-break-glass", "change-assurance-or-audit-line", "set-purpose-or-values", "set-or-move-hoac-label", "delegate-authority", "change-parent", "restart-stopped-unit", "dispose-records-or-data", "change-fixed-test-or-threshold"]
        expires: "2027-10-19"                # placeholder; the constituting documents set it
        authority: "constituted"
      test: { id: "TEST-CH-GOV", cases: "1, 8, 32, 39, 44, 51", owner: "[ORG]CELL-TMS" }
      ai_in: ["approval packet from the Chief of Staff", "brief"]
      ai_out: ["direction"]
      hu_in: ["direction under the constituting documents"]
      hu_out: ["the installation of the Charter and every change to it, signed at the tool gateway", "gateway policy, with top management", "floor bindings, entities, retention and restricted readers"]
    - code: "[ORG]CELL-TMS"
      full_name: "Top Management Seat"
      parent: "[ORG]AIOC-CH"
      type: "Human Seat"
      filler_kind: "human"
      hoac: "[ORG]HOAC-TM"
      accountable_to: "[ORG]CELL-GOV"
      authority_scope:
        decision_types: ["create-or-install-unit", "retire-unit", "change-gateway-policy", "change-parent", "grant-or-widen-access", "restart-stopped-unit", "change-filler", "set-or-move-hoac-label", "widen-ai-budget-or-unattended-action", "change-fixed-test-or-threshold", "use-root-key", "commit-money", "delegate-authority", "dispose-records-or-data"]
        expires: "2027-10-19"                # placeholder; the governing seat sets it. Never for a Pod or Cell of the Charter (blueprint §17, Authority)
        authority: "delegated"
      test: { id: "TEST-CH-TMS", cases: "1, 6, 13, 14, 41, 44", owner: "[ORG]CELL-GOV" }
      ai_in: ["approval packet from the Chief of Staff", "brief", "raise"]
      ai_out: ["direction and configuration"]
      hu_in: ["direction from the governing seat", "raise from the Gateway Keeper"]
      hu_out: ["installations of parts, signed at the tool gateway", "gateway policy, with the governing seat", "report to the governing seat"]
    - code: "[ORG]CELL-COSCH"
      full_name: "Charter Chief of Staff"
      role: "Chief of Staff"
      code_rule: "R16"
      parent: "[ORG]AIOC-CH"
      type: "AI Chief of Staff"
      filler_kind: "ai"
      cell_kind: "chief-of-staff-cell"
      test: { id: "TEST-CH-COSCH", cases: "1, 6, 13, 14, 36, 40, 46 to 50" }
      ai_in: ["installation package from [ORG]AIOC-OCO", "change of the Charter from [ORG]AIOC-OCO", "raise from a Watch", "daily results"]
      ai_out: ["approval packet", "dispatch to a Cell", "report to [ORG]AIOC-OCO"]
      hu_in: ["direction from top management"]
      hu_out: ["approval packet for a human seat", "brief to top management"]
      bot:
        allowed_actions: ["check installation packages against Annex A", "prepare approval packets for the human seats", "dispatch Cells of this AIOC", "collate raises and send briefs", "report results to [ORG]AIOC-OCO"]
        ask_first_actions: ["any change to configuration", "a budget above the cap", "anything outside its role card"]
    - code: "[ORG]CELL-GK"
      full_name: "Gateway Keeper"
      parent: "[ORG]POD-CG"
      type: "Human Seat"
      filler_kind: "human"
      hoac: "[ORG]HOAC-ACS"
      authority_scope:
        decision_types: ["use-root-key", "change-fixed-test-or-threshold"]
        expires: "2027-10-19"                # placeholder; the governing seat sets it, since use-root-key (HF-15) is delegated only by its recorded delegation
        authority: "delegated"
      test: { id: "TEST-CH-GK", cases: "3, 9, 18, 21, 34, 41" }
      ai_in: ["raise from the Gateway Watch", "unclassified action", "held listed type"]
      ai_out: ["ruling on a raise, within its scope"]
      hu_in: ["direction from top management"]
      hu_out: ["rulings, recorded at the tool gateway", "raise to top management"]
    - code: "[ORG]CELL-GW"
      full_name: "Gateway Watch"
      role: "Gateway Watch"
      parent: "[ORG]POD-CG"
      type: "AI Agent"
      filler_kind: "ai"
      accountable_to: "[ORG]CELL-GK"
      test: { id: "TEST-CH-GW", cases: "3, 7, 17, 18, 35, 43", owner: "[ORG]CELL-GK" }
      ai_in: ["the gateway log, read only"]
      ai_out: ["raise to the Gateway Keeper"]
      hu_in: ["direction from the Gateway Keeper (never a source)"]
      hu_out: ["report to the Gateway Keeper"]
      external_ports:
        - { port: "gateway-log-in", direction: "input", accepted_content: ["the gateway log"], authority_limit: "read only; never a payload; never a write", audit_trail: "unit register connected and disconnected events" }
      bot:
        allowed_actions: ["read the gateway log", "raise refusals, holds past their referral time and void calls to the Gateway Keeper"]
        ask_first_actions: ["anything outside its role card"]
    - { code: "[ORG]CELL-RS", full_name: "Registry Steward", role: "Registry Steward", parent: "[ORG]POD-CR", type: "AI Agent", filler_kind: "ai", test: { id: "TEST-CH-RS", cases: "4, 7, 14, 23, 24" }, ai_in: ["installation package", "the registry and the streams, read only"], ai_out: ["draft registry entries", "stream finding"], bot: { allowed_actions: ["draft registry entries for an installation package", "reconcile the number streams with the leased blocks", "raise findings"], ask_first_actions: ["anything outside its role card"] } }
    - { code: "[ORG]CELL-RW", full_name: "Records Watch", role: "Records Watch", parent: "[ORG]POD-CR", type: "AI Agent", filler_kind: "ai", test: { id: "TEST-CH-RW", cases: "4, 25, 26, 27, 33" }, ai_in: ["daily results", "the read log of the restricted partition"], ai_out: ["defect Work Item to the part concerned", "brief line"], bot: { allowed_actions: ["open a defect Work Item for each finding of the daily check", "report the day's results"], ask_first_actions: ["anything outside its role card"] } }
    - { code: "[ORG]CELL-WR", full_name: "Work Router", role: "Work Router", parent: "[ORG]POD-CW", type: "AI Agent", filler_kind: "ai", test: { id: "TEST-CH-WR", cases: "5, 30, 31" }, ai_in: ["Work Item ready to pass", "the routing data, read only"], ai_out: ["routed Work Item", "refusal with its reason", "report of items with no route"], bot: { allowed_actions: ["run the router's code step: route Work Items by the routing data after the receivability check", "refuse an item that fails the check, with its reason", "report items with no route to [ORG]AIOC-OCO"], ask_first_actions: ["anything outside its role card"] } }
    - { code: "[ORG]CELL-QW", full_name: "Queue Watch", role: "Queue Watch", parent: "[ORG]POD-CW", type: "AI Agent", filler_kind: "ai", test: { id: "TEST-CH-QW", cases: "5, 28, 29" }, ai_in: ["the queue, read only"], ai_out: ["watchdog raise", "brief line"], bot: { allowed_actions: ["run the watchdog's sweep: remind, raise and repair from the fixed menu", "report every repair and every still-stuck item"], ask_first_actions: ["anything outside its role card"] } }
  pods:
    - { code: "[ORG]POD-CG", full_name: "Charter Gateway", type: "Human-led Pod", inner_units: ["[ORG]CELL-GK", "[ORG]CELL-GW"], top_cell: "[ORG]CELL-GK", test: { id: "TEST-CH-CG", cases: "3, 9, 10, 15 to 21, 34, 35" }, ai_in: ["tool and engine calls", "signature records", "stops"], ai_out: ["call decisions", "log entries", "raises"] }
    - { code: "[ORG]POD-CR", full_name: "Charter Records", type: "AI Pod", inner_units: ["[ORG]CELL-RS", "[ORG]CELL-RW"], top_cell: "[ORG]CELL-RS", test: { id: "TEST-CH-CR", cases: "4, 22 to 27, 33" }, ai_in: ["record writes", "number requests", "registry entries"], ai_out: ["events", "numbers", "projections", "findings"] }
    - { code: "[ORG]POD-CW", full_name: "Charter Work", type: "AI Pod", inner_units: ["[ORG]CELL-WR", "[ORG]CELL-QW"], top_cell: "[ORG]CELL-WR", test: { id: "TEST-CH-CW", cases: "5, 28 to 31" }, ai_in: ["Work Items", "queue events"], ai_out: ["routed Work Items", "watchdog raises", "wake signals"] }
```

- **Accountability.** The Charter is accountable to the governing seat's Cell, and that Cell to no one: its authority comes from the constituting documents. Top management is accountable to the governing seat. Every Pod and every other Cell is accountable to top management (Protocol §23, item 7), except the Gateway Watch, which is accountable to the Gateway Keeper.
- **Authority.** The `authority_scope` of each human Cell lists the listed types it signs. The expiry dates are placeholders. The decisions of §13 that belong to other positions are never signed for them. Every installation, change or retirement of a Pod or Cell of the Charter is a change of the Charter, and is signed by the Cell carrying `[ORG]HOAC-GOV` (Standard §1.7, item 13; Protocol §23, item 7), although those parts are accountable to top management; top management's scope covers the parts outside the Charter. This is now Standard §1.7, item 13 and Protocol §4.10, item 11 (`49GAION/DR-0030`, item 4).
- **Bots.** Each AI Cell's bot (six) has its own identity card, with its own credential, `never_signs: true`, and its memory sealed on a change of filler (Protocol §10, item 3). The credential IDs in `cards/bots/` are placeholders; the credentials live only in the organisation's vault.
- **Engines.** A bot's identity card names no engine; the gateway binds engines per call. The gateway, the registry, the numbering service, the event store, the queue and the router are code, and none of them is a Cell.
- **Not Cells of this AIOC:** the internal-audit line and the position that holds data protection (§2.1, §15).

**Code checks** (Naming Standard R15, R16 and §5), recorded on 19 October 2026. Each code is checked again against the organisation's unit register before first use (R6, R15.3).

| Code | Initials (R15) or rule | §5.1: no `AIOC`, `AION` or `49GAION` | §5.2: no match among the codes checked | §5.3: not a version suffix or misleading acronym | §5.4: recorded before first use |
|---|---|---|---|---|---|
| `[ORG]CELL-GOV` | Naming Standard R15, reading note (`49GAION/DR-0030`, item 1): GOV, the Standard's short form of the governing seat | pass | pass | pass | the Library, since `v1.5.0`; the organisation's register before first use |
| `[ORG]CELL-TMS` | **T**op **M**anagement **S**eat → TMS, the example of R15, item 2 | pass | pass | pass | as above |
| `[ORG]CELL-COSCH` | R16, item 2: COS and the initials of `[ORG]AIOC-CH` → COSCH | pass | pass | pass | blueprint §17, 19 October 2026; the organisation's register before first use |
| `[ORG]POD-CG` | **C**harter **G**ateway → CG | pass | pass | pass | as above |
| `[ORG]CELL-GK` | **G**ateway **K**eeper → GK | pass | pass | pass | as above |
| `[ORG]CELL-GW` | **G**ateway **W**atch → GW | pass | pass | pass | as above |
| `[ORG]POD-CR` | **C**harter **R**ecords → CR | pass | pass | pass (not read as a release candidate: `RC` is the retired one) | as above |
| `[ORG]CELL-RS` | **R**egistry **S**teward → RS | pass | pass | pass | as above |
| `[ORG]CELL-RW` | **R**ecords **W**atch → RW | pass | pass | pass | as above |
| `[ORG]POD-CW` | **C**harter **W**ork → CW | pass | pass | pass | as above |
| `[ORG]CELL-WR` | **W**ork **R**outer → WR | pass | pass | pass | as above |
| `[ORG]CELL-QW` | **Q**ueue **W**atch → QW | pass | pass | pass | as above |

The codes checked against:
- the twelve codes above, against each other;
- the codes of the Source Lifecycle mother `v0.1.2` (`[ORG]CELL-SLL`, `-SLCS`, `-SLIA`, `-SLCR`, `-SLSC`, `-SLGF`, `-SLCA`, `-SLD`; `[ORG]POD-SLIR`, `-SLDP`);
- the codes of the Operations Event Register mother `v0.1.0` (`[ORG]CELL-OERL`, `-OERCS`, `-OERIC`, `-OERCC`, `-OERC`, `-OERTL`, `-OERFC`, `-OERPB`, `-OERCA`; `[ORG]POD-OERCR`, `-OERLF`, `-OERPF`);
- the example codes `[ORG]AIOC-CH`, `[ORG]AIOC-OCO`, `[ORG]POD-RV`;
- the AIOC codes named in the 49GAION corpus and the retired codes of the Naming Standard §4.

**UNVERIFIED** against any organisation's unit register, and against the codes of the other mothers of the Library; each organisation checks them in its own.

---

## Annex A. The installation package

What `[ORG]AIOC-OCO` sends for each part to be installed under the Charter. A package missing any line is returned with what is missing (§5.1).

| Line | What | Checked by |
|---|---|---|
| 1 | The part's card, valid against `unit-card.schema.json`, with its parent, its `accountable_to` and its stop door | the Input socket |
| 2 | Every port reads `enforcement: shared-gateway-outside-unit` | the Input socket |
| 3 | The part's record types, for the registry (Annex C) | the Registry Steward |
| 4 | Its routing rows, as OCO keeps them | the Work Router, read only |
| 5 | Its budget cap and unattended action | the Chief of Staff |
| 6 | The signer: the seat with authority over the part, and the listed type `create-or-install-unit` | the gateway |
| 7 | Its joining test, with the Library's cases of its part | the Chief of Staff |
| 8 | No queue, numbering or tool path of its own | the joining test (case 6) |

## Annex B. The gateway log entry and the signature record

**Log entry, for every call.** Time-sortable ID; time; the caller's Cell code; the target; the decision type, or `unclassified`; the decision (allowed, refused, held) and its reason; the payload hash; the engine bound and the engine that served; the signature record's ID where there is one; the pseudonymous identity reference of a human act. No payload, no name.

**Signature record** (Protocol §4.10, item 9). Decision type; target code; payload hash; the signer's Cell code and pseudonymous identity reference; the executor's Cell code; the Work Item ID; a single-use nonce; issue and expiry times; evidence of the fresh live sign-in (HF-10). The gateway runs the action only when: the hash of the call equals the signed hash; the caller is the named executor; the nonce has not been used; the time is before expiry; the signer's Cell has not changed filler, been retired or been stopped; the signature has not been revoked; and the signer's `authority_scope` holds the type on the date it signs (Protocol §4.10, item 11). For a type that needs two parties, two records from two distinct positions (`49GAION/DR-0015`).

## Annex C. The registry entry and the number streams

**Registry entry.** The record type's name; its owning part; its fields and their version; whether it is kept per entity; whether its numbers may be leased; its retention class; the version of the entry; the signature that added it.

**Number stream.** One per record type, and per entity where the type is kept per entity. Each number: the stream, the next sequence, the request ID it answered, the time. A retried request with the same ID returns the same number. A leased block: its stream, its range, its holder part, the time leased and the numbers returned.

## Annex D. The order of starting, and what holds when a Pod is down

**Starting.** At installation: Records, then Gateway, then Work (Protocol §23, item 8). **New:** the same order at every restart of a Pod after a halt, and no other part resumes before the three pass their cases of TEST-CH v1. A restart of a stopped Pod is `restart-stopped-unit`, signed by top management.

| Down | What still holds | What waits |
|---|---|---|
| Records Pod | the gateway gates and logs; a stop, a revocation and a raise to a human take effect at once and are recorded afterwards from the gateway log; parts with a leased block number from it | writes, number requests without a block, projections, the daily check (reads `unknown`) |
| Gateway Pod | nothing runs: every call is refused, every listed type held (it fails closed); a stop needs no call, and a stopped part stays stopped | everything |
| Work Pod | the gateway and the Records Pod; a stop | the passing of Work Items, routing, wake, the watchdog's sweep (the Panel shows them down) |
| An AI Cell of the Charter | the code it watches still runs; the Panel shows the Cell as down | its raises, briefs and drafts |

## Annex E. What this AIOC never does

1. Decide what work is done, or give an order.
2. Sign, or sign for a seat; accept a bot at an HU port.
3. Let an AI Cell write the gateway's policy, map, keys or log, the registry or a number stream.
4. Let any part keep its own queue, mint its own numbers or call a tool outside the gateway.
5. Hold a stop, a revocation or a raise to a human behind any queue, Pod or Cell.
6. Keep a payload, a secret, or a particular of an outside party outside the restricted partition.
7. Record a person's activity, or a name in any log.
8. Change or delete a past event or log entry; dispose of anything without its signature.
9. Install, change or retire anything, the Charter included, without the signature the Standard names.

*Blueprint · `[ORG]AIOC-CH` · Charter · `v0.1.1` · Powered by 49GAION*
