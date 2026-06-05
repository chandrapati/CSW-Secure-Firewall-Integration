# FAQ

> **Cisco source.** [Deep Dive of Secure Workload & Firewall Integration](https://secure.cisco.com/secure-workload/docs/secure-workload-whitepaper) — FAQ section. Confirm against your licensed releases.

---

### What if I have a mix of agent-based and agentless workloads behind a firewall mapped to the FMC connector?

The integration's intent is to protect **agentless** workloads, but a mix still works.
The difference: rules for the **agent-based** workloads (which already enforce via the
host OS firewall) will **also** be pushed to the FMC Access Control Policy — a
byproduct of Secure Workload's **hierarchical policy engine**.

### Can I map more than one Scope to an ACP?

**No.** Only **one Scope** can be mapped to **one ACP**.

### Can I add Layer 7 capabilities / other FMC features to Secure Workload-controlled rules?

**No (not supported).** Secure Workload rules are orchestrated from Secure Workload and
shouldn't be modified. You *can* technically add FMC features, but it's **not advised
and not supported** — at the time of writing the use case is **east-west
microsegmentation with L3/L4 policies**.

> Need true L7 / URL / FQDN-path segmentation? That's a different tool — see the
> FQDN/URL discussion in **CSW-Policy-Lifecycle** (`docs/06-fqdn-and-domain-policy.md`).

### How do I get dual-management (Secure Workload-owned **and** FMC-owned policies)?

Use **Merge** mode — Secure Workload **honors existing FMC rules**. Choose to place
CSW rules on **top** or **bottom** of existing ones, then **preserve that rule
ordering** to keep both authoring models intact. If a CSW-owned rule is moved or
modified, Secure Workload **overrides the change** and restores the original state.

### What happens if a rule owned by Secure Workload is modified?

Secure Workload **overrides** the change and returns it to the original state.

### Which FMC versions are supported?

| Capability | Minimum FMC |
|---|---|
| **Dynamic objects** | **≥ 7.0.1** |
| **Virtual patch** | **≥ 7.2** |
| Engineering-qualified releases cited | **7.0.1** and **7.2.5** |

> Versions are from the whitepaper ("updated over 2 years ago"). **Confirm current
> support** for your CSW and FMC releases before designing a rollout.

---

## See also

- [`docs/00-official-references.md`](./00-official-references.md)
- [`docs/04-fmc-connector-and-policy.md`](./04-fmc-connector-and-policy.md) — merge/override mechanics
