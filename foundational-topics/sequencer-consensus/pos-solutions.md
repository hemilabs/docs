# PoS Solutions

{% hint style="info" %}
## 📜 **TL;DR:**

* The Hemi Network combines **Proof-of-Stake (PoS)** with **Proof-of-Proof (PoP)** for enhanced security which:
  * **Protects against weak subjectivity** using Bitcoin's state proofs.
  * **Prevents censorship attacks** by offloading transactions to Bitcoin.
{% endhint %}

***

## 🛡️ Against Weak Subjectivity

Even if an attacker gathers old staking keys, they can't alter the state proofs on the Bitcoin blockchain. These state proofs confirm the Hemi Network's transaction history, so any fake blockchain the attacker creates would be recognized as invalid.

***

## 🚫 Against Censorship Attacks

In a worst-case scenario where an attacker controls all the sequencers (the nodes that create blocks in the blockchain), the Hemi Network can still function by using the Bitcoin network.

Transactions can be processed (or "offloaded") to Bitcoin, which prevents the attacker from having total control.

***

## 🔚 Conclusion

The Hemi Network’s hybrid **PoS-PoP consensus model** hardens the network protocol against both weak subjectivity and censorship. Even with an overwhelming majority of old staking keys, an attacker would be unable to forge finalized state proofs on the Bitcoin blockchain, and the established state proofs would invalidate the altered Hemi Network chain.
