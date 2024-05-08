# Pros & Cons

{% hint style="info" %}
## 📜 **TL;DR:**

* Optimistic Rollups: Faster, presumed valid until proven otherwise; has delays, user fraud detection, relies on centralization.
* Zero-knowledge Rollups: Prior validation is needed, enhanced privacy; complex vulnerabilities, trusted setup, reliance on centralization.
* Centralized Influence: Centralized proposers could disrupt decentralized frameworks.
* Verifiers and Challenges: Vulnerabilities demand verifiers, lack of incentives leads to centralization.
* Denial-of-Service Risks: Centralized "batchers" in L2 networks risk refusing to publish transactions back to Ethereum, potentially causing service denial.
{% endhint %}

***

## 🌀 **Conventional Rollups**

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Optimistic Rollups</strong></td><td><p>✅ Pros:</p><ul><li>Allows faster transaction processing on Layer 2.</li><li>Presumes transactions are valid unless disputed within a specific period.</li><li>Reduces congestion on the main chain (L1).</li></ul></td><td><p>❌ Cons:</p><ul><li>Introduces delays due to the challenge period for dispute resolution.</li><li>Places the responsibility of fraud detection on users.</li><li><em><strong>Relies on centralized sequencers and proposers, causing hidden transaction queues (mempools) and centralized chain state communication.</strong></em></li></ul></td></tr><tr><td><strong>Zero-knowledge Rollups</strong></td><td><p>✅ Pros:</p><ul><li>Validates transactions before confirming them on the main chain (L1).</li><li>Potentially enables privacy features by leveraging zk proofs, although current implementations like ZkSync, the largest zk rollup-based L2, do not currently incorporate significant privacy features.</li><li>Reduces congestion on the main chain (L1).</li></ul></td><td><p>❌ Cons:</p><ul><li>Potential vulnerabilities in complex cryptographic systems.</li><li>Often requires a trusted setup for implementation.</li><li><em><strong>Relies on centralized sequencers and proposers, causing hidden transaction queues (mempools) and centralized chain state communication.</strong></em></li></ul></td></tr></tbody></table>

***

## 💭 Things to Consider

### Centralized Influence in a Decentralized Sequencing World

Within frameworks aiming for decentralized sequencing, the presence of a centralized proposer could wield significant influence, \*\*potentially disrupting the intended decentralized nature. \*\*

Such control might result in the withholding of valid state rollups from Ethereum, leading to coercion of decentralized sequencers into potential censorship or halting communication of specific chain segments back to Ethereum for settlement.

***

### Verifiers and Challenges

Vulnerabilities in optimistic rollup networks pose risks of asset theft through forged L2 states. To address this, rollups introduce verifiers, but the lack of proper incentives for this role presents challenges.

These lack of incentives can lead to difficulties such as:

* 🔒 Securing a sufficient number of verifiers to perform the complex and expensive verification process required.
* 👥 Relying heavily on users or nodes funded by development teams resulting in centralization.
* 📣 Potential bias or influence.
* 🌎 Sustainability and scalability issues.

***

### Denial-of-Service Risks

L2 networks' reliance on centralized "batchers" can expose them to denial-of-service risks if batchers refuse to publish transactions back to Ethereum for data availability.
