---
description: How to get help, report bugs, and disclose security vulnerabilities to Hemi.
---

# Support and Bug Reports

### Getting Help

| Issue                                             | Where to report                                                                                                                                                                     |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| General support                                   | <p><a href="https://discord.gg/hemixyz">Hemi Discord</a> — <code>#support</code> or <code>#create-ticket</code><br>Email <a href="mailto:support@hemi.xyz">support@hemi.xyz</a></p> |
| Partnership inquiries                             | Email [partners@hemi.xyz](mailto:partners@hemi.xyz)                                                                                                                                 |
| Bugs in Hemi services (app, explorer, etc.)       | [Hemi Discord](https://discord.gg/hemixyz) — `#create-ticket`                                                                                                                       |
| Bugs or feature requests for open-source software | Open a [GitHub Issue](https://github.com/hemilabs) on the relevant repository                                                                                                       |
| Security vulnerabilities                          | [See below](contact.md#security-vulnerabilities)                                                                                                                                    |

### Security Vulnerabilities

If you've found a security vulnerability in Hemi, we want to hear about it.

{% hint style="danger" %}
**Do not** test against production systems, disclose vulnerabilities publicly, or report them in GitHub issues. Doing so puts users at risk, may violate applicable law, and will disqualify you from rewards.\
\
Denial-of-service testing, social engineering, and volumetric attacks are explicitly out of scope and prohibited. **All security research must be conducted in accordance with the policies outlined in our** [**Bugcrowd program**](https://bugcrowd.com/engagements/hemi)**.**
{% endhint %}

#### How to Report

All vulnerability reports **must** be submitted through our official [Vulnerability Disclosure Program on Bugcrowd](https://bugcrowd.com/engagements/hemi). We do not accept vulnerability reports via email, Discord, social media, or any other channel. Reports submitted outside of Bugcrowd will not be reviewed or eligible for rewards.

When reporting, the more information you can provide, the faster we can triage and confirm the vulnerability. Reports with clear reproduction steps and screenshots are highly valued.

#### Bug Bounty Program

Hemi also operates a private Bug Bounty program on Bugcrowd with paid rewards. Researchers who submit high-quality reports through our Vulnerability Disclosure Program may be invited to participate at Hemi's discretion.

#### Responsible Disclosure

Please do not discuss any vulnerabilities outside our Bugcrowd program without express consent from Hemi Labs. Follow our [program disclosure policy](https://bugcrowd.com/engagements/hemi) for full details.

Hemi provides Safe Harbor for security research conducted in good faith under our program policy. See the full Safe Harbor terms on our [Bugcrowd program page](https://bugcrowd.com/engagements/hemi).

{% hint style="info" %}
For other security-related questions or concerns, please contact [security@hemi.xyz](mailto:security@hemi.xyz).
{% endhint %}

#### Out-of-Scope Notes

Some behaviour that looks like a finding is intentional. The items below are documented here so researchers do not spend time on known non-issues.

<details>

<summary><code>txpool_*</code> JSON-RPC methods on <code>op-geth</code> are intentionally exposed</summary>

The `txpool_*` RPC namespace is intentionally exposed on our op-geth nodes and is out of scope for information-disclosure vulnerabilities.

**Why these methods are exposed:**

* They are read-only. They report on transactions that are pending or queued in the node's transaction pool. They do not modify state, move funds, sign anything, or control the node.
* The data they return is already public. Pending and queued transactions are gossiped across the public P2P network, so any connected peer observes the same transactions as they propagate. Serving this data over RPC does not reveal anything that a mempool participant cannot already see.
* We rely on this namespace for operational monitoring, mempool observability, and developer and dApp integrations that need visibility into pending transactions.

**What this means for reports:**

* A report whose only finding is that `txpool_*` methods are reachable, or that they return mempool contents, will be closed as out of scope. The public nature of the mempool is a property of the network, not a misconfiguration.

Still worth reporting are:

* A `txpool_*` method returning data that is genuinely not public.
* Findings against other RPC namespaces such as `admin_*`, `debug_*` . These are evaluated separately and not covered by this note.

</details>
