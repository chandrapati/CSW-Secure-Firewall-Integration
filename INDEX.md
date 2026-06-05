# Index — find it fast

Quick navigation for the Secure Workload + Secure Firewall integration guide.

## By topic

| Topic | Doc |
|---|---|
| Why integrate; host vs network enforcement; 3 use cases | [`docs/01-overview.md`](./docs/01-overview.md) |
| Topology Awareness — scope ↔ firewall mapping, compliance | [`docs/02-topology-awareness.md`](./docs/02-topology-awareness.md) |
| Architecture; NSEL; Ingest connector; flow stitching | [`docs/03-architecture-and-visibility.md`](./docs/03-architecture-and-visibility.md) |
| FMC connector; ADM discovery; ACP↔scope; merge/override; dynamic objects; compliance alerts | [`docs/04-fmc-connector-and-policy.md`](./docs/04-fmc-connector-and-policy.md) |
| Insertion options — L2/L3/ACI, AWS/Azure/GCP | [`docs/05-insertion-options.md`](./docs/05-insertion-options.md) |
| Virtual patch (CVE export → IPS) | [`docs/06-virtual-patch.md`](./docs/06-virtual-patch.md) |
| Rapid Threat Containment | [`docs/07-rapid-threat-containment.md`](./docs/07-rapid-threat-containment.md) |
| FAQ; supported versions | [`docs/08-faq.md`](./docs/08-faq.md) |
| Official Cisco references | [`docs/00-official-references.md`](./docs/00-official-references.md) |
| Figure attribution | [`assets/figures/NOTICE.md`](./assets/figures/NOTICE.md) |

## By question

| If you're asking… | Go to |
|---|---|
| *"I can't install an agent — can I still segment this?"* | [`docs/01-overview.md`](./docs/01-overview.md) — yes, network-based via Secure Firewall |
| *"How does Secure Workload see agentless traffic?"* | [`docs/03-architecture-and-visibility.md`](./docs/03-architecture-and-visibility.md) — NSEL + Ingest connector |
| *"How does it avoid junk rules in my firewall audit?"* | [`docs/02-topology-awareness.md`](./docs/02-topology-awareness.md) — one Scope per firewall ACP |
| *"Will it overwrite my existing FMC rules?"* | [`docs/04-fmc-connector-and-policy.md`](./docs/04-fmc-connector-and-policy.md) — Merge vs Override |
| *"One firewall protects several apps — how do I map it?"* | [`docs/04-fmc-connector-and-policy.md`](./docs/04-fmc-connector-and-policy.md) — parent vs child scope |
| *"Where should the firewall sit (L2/L3/ACI/cloud)?"* | [`docs/05-insertion-options.md`](./docs/05-insertion-options.md) |
| *"Can it help with an unpatchable CVE?"* | [`docs/06-virtual-patch.md`](./docs/06-virtual-patch.md) — virtual patch via IPS |
| *"Can it auto-quarantine a compromised workload?"* | [`docs/07-rapid-threat-containment.md`](./docs/07-rapid-threat-containment.md) |
| *"Can I add L7 / URL rules to these firewall policies?"* | [`docs/08-faq.md`](./docs/08-faq.md) — no (L3/L4 only) |
| *"Which FMC versions do I need?"* | [`docs/08-faq.md`](./docs/08-faq.md) — dynamic objects ≥7.0.1, virtual patch ≥7.2 |
