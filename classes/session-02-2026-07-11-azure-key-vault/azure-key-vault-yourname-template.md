# My Notes — Okeke Marycynthia

## Key Concepts I Learned

Azure Key Vaults & Defense-in-Depth
* During this class, I gained a better understanding of how Azure Key Vault strengthens security by providing a centralized location for storing and managing sensitive information.

* I learned that Azure Key Vault is the recommended service for securely storing secrets, encryption keys, and certificates instead of embedding them in applications or configuration files.

* I also learned about the importance of key rotation, centralized secret versioning, and monitoring suspicious access patterns with Microsoft Defender. These practices help reduce the risk of compromised credentials and improve an organization's overall security posture.

* One important takeaway was understanding how the exposure of a single secret can potentially lead to the compromise of an entire workload if proper security controls are not in place.

* For certificate management, Azure Key Vault can integrate with DigiCert and GlobalSign for certificate issuance and lifecycle management. However, an organization must maintain a separate account with either provider, as these services are not automatically included with Microsoft Azure.

Azure Key Vault Authorization Models
I learned that Azure Key Vault supports two authorization planes:
1. Control Plane – Used to manage the Key Vault resource itself (creation, configuration, deletion, and access management).
2. Data Plane – Used to access the data stored inside the vault, such as secrets, keys, and certificates.
   
Azure RBAC (Role-Based Access Control)
Azure RBAC is the modern and recommended authorization model for Azure Key Vault because it:
1. Provides a unified access management model across Azure resources.
2. Supports scoped and auditable role assignments.
3. Integrates seamlessly with managed identities.
4. Simplifies access management compared to older permission models.
   
Legacy Access Policies
I also learned about Legacy Access Policies, which:
1. Use a separate permission model for each Key Vault.
2. Can introduce policy drift over time due to inconsistent configurations.
3. Are still available in many existing Azure environments but are gradually being replaced by Azure RBAC.

Core Components of Azure Key Vault
Azure Key Vault is designed to manage three primary types of sensitive assets:
1. Secrets
-Used to securely store sensitive information such as:

2. Passwords
-API keys
-Connection strings

3. Keys
-Used for cryptographic operations, including:
a. Encryption
b. Decryption
c. Digital signing

3. Certificates
-Used to manage X.509 certificates and support their issuance, storage, and renewal throughout their lifecycle.

Managed Identities
I learned about the two types of managed identities available in Azure:
-System-Assigned Managed Identity
*Created and enabled directly on an Azure resource.
*The identity has the same lifecycle as the resource.
*Intended for use by a single Azure resource.

-User-Assigned Managed Identity
*Created as an independent Azure resource.
*Can be assigned to multiple Azure resources.
*Enables identity reuse across different services and workloads.
*Data Protection and Network Security Controls

I also learned about several security features that help protect Azure Key Vault:
1. Firewall and Network Access – Restricts access to the Key Vault using network rules and private connectivity.
2. Soft Delete and Purge Protection – Prevents accidental or malicious deletion of vault contents by allowing recovery and protecting against permanent removal.
3. Operational Guard Rails – Provides built-in safeguards and governance features that help maintain secure configurations and reduce operational risks.
-
-

---

## Lab / Hands-On Work

<!-- Describe what you did in the lab. Include steps, commands, or screenshots descriptions -->

### What I did


### What happened / Result


### Challenges I faced


---

## My Takeaways

<!-- What was most valuable to you personally from this session? -->


---

## Questions I Still Have

<!-- Anything you want to follow up on or ask the mentor -->

-
-

---

## Resources I Found Useful

<!-- Any links, docs, or Microsoft Learn modules you found helpful -->

-

---

*Submitted by: Marycynthia Okeke · Nechy_Okeke*
