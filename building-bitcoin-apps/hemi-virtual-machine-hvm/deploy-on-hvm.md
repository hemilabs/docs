# Deploy on hVM

{% hint style="info" %}
## 📜 **TL;DR:**

* To use hVM directly, you will have to call the appropriate precompile address with the appropriate serialized bytes to pass parameters to the function.&#x20;
* Most dApp developers will use the Hemi Bitcoin Kit (hBK) **rather** than hVM directly.&#x20;
{% endhint %}

***

## 🌐 Overview

* To use hVM directly, you will have to call the appropriate precompile address with the appropriate serialized bytes to pass parameters to the function.&#x20;
* Each successful precompile call will return serialized bytes according to the precompile’s return data specification.

***

## 🟨 Developer Tip

> **Most dApp developers will use the Hemi Bitcoin Kit (hBK) rather than hVM directly.**&#x20;

* If you’re looking for an easy way to get started developing Bitcoin-aware dApps on Hemi, check out the “Hemi Bitcoin Kit (hBK)” section. Understanding how Bitcoin Kit uses hVM under-the-hood may be helpful, and dApp developers looking to maximize gas efficiency may benefit from using hVM directly to avoid paying overhead for unmarshalling data they don’t need for a specific use case.

###
