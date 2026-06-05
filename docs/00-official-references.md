# Official Cisco References

The canonical Cisco sources behind this repo. When in doubt, these win — this
repo is a practitioner's distillation, not an official Cisco publication.

---

## Primary sources (the three articles)

| Topic | Cisco article |
|---|---|
| **Overview** — host vs network enforcement; the 3 use cases | [Secure Workload and Secure Firewall — Overview](https://secure.cisco.com/secure-workload/docs/secure-workload-and-secure-firewall) |
| **Topology Awareness** — scopes, scope↔firewall mapping, FMC connector | [Secure Workload — Importance of Topology Awareness](https://secure.cisco.com/secure-workload/docs/secure-workload-compliance) |
| **Deep dive** — architecture, NSEL/Ingest connector, FMC connector, insertion options, virtual patch, rapid threat containment | [Deep Dive of Secure Workload & Firewall Integration](https://secure.cisco.com/secure-workload/docs/secure-workload-whitepaper) |

---

## Supporting product documentation

| Topic | Cisco document |
|---|---|
| Connectors (Ingest / NSEL, FMC, Secure Connector) | [Secure Workload Connectors (4.0)](https://www.cisco.com/c/en/us/td/docs/security/workload_security/secure_workload/user-guide/4_0/cisco-secure-workload-user-guide-on-prem-v40/connectors.html) |
| Policy lifecycle (rank, inheritance, scopes) | [Manage Policy Lifecycle (4.0)](https://www.cisco.com/c/en/us/td/docs/security/workload_security/secure_workload/user-guide/4_0/cisco-secure-workload-user-guide-on-prem-v40/manage-policy-lifecycle-in-secure-workload.html) |
| FMC / Secure Firewall | [Cisco Secure Firewall Management Center docs](https://www.cisco.com/c/en/us/support/security/defense-center/series.html) |

---

## Key facts these sources establish (cited throughout)

- **Two enforcement approaches, one policy.** Host-based (agent) and network-based
  (Secure Firewall via FMC) are authored in the same Secure Workload scope model.
- **Visibility via NSEL.** Secure Workload ingests **NSEL** (NetFlow Secure Event
  Logging) from Secure Firewall — stateful, bi-directional flow tracking — through
  the **Ingest Connector** (scales to **45k fps** per firewall connector, up to
  **135k fps** per appliance on-prem). Flow stitching reconstructs end-to-end flows
  even through NAT.
- **Policy push via FMC connector.** Validated policies push to **FMC** as
  **dynamic objects** (no redeploy when an object changes). SaaS/behind-proxy
  deployments need the **Secure Connector**.
- **Topology Awareness.** Each firewall onboards on an **Access Control Policy
  (ACP)** basis by **mapping one ACP to one Scope**, so only relevant rules are
  pushed.
- **Supported FMC versions.** Dynamic objects: **FMC ≥ 7.0.1**. Virtual patch:
  **FMC ≥ 7.2**. Engineering-qualified releases cited: **7.0.1 and 7.2.5** (as of
  the whitepaper — confirm current).

---

## Versioning note

The three articles were published under **Release 3.9 & older** and updated
"over 2 years ago" relative to capture. Capabilities and supported FMC versions
evolve — **always confirm against the CSW and FMC releases you run** before
designing an enforcement rollout.
