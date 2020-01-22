<img src="https://education-yh.s3-us-west-2.amazonaws.com/Vault_Icon_FullColor.png" alt="Logo"/>

If you are new to Vault, please complete the [Vault Operations](https://www.katacoda.com/hashicorp/scenarios/vault-operations) first, and then proceed with this Katacoda scenario to better understand the workflow.

-----

[Vault Deployment Guide](https://learn.hashicorp.com/vault/day-one/ops-reference-architecture) recommended Vault to use [Consul](https://www.consul.io/) as its storage backend. The challenge is that when Vault encounters an outage, the root cause may be the storage backend. Therefore, you had to troubleshoot two different system to bring Vault to a healthy state.

In Vault 1.3, an integrated storage was introduced to persist the encrypted data. The [***Raft***](https://github.com/hashicorp/raft) algorithm used in Consul is directly embedded into Vault to provide a built-in storage.

> **NOTE:** Vault Integrated Storage is currently in ***BETA*** mode; therefore, not suitable for deployment in production.
