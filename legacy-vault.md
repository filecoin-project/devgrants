# Filecoin Open Grant Proposal: Legacy Vault

* **Project Name:** Legacy Vault
* **Category:** Application / Security / Developer Tooling
* **Target Audience:** General public, crypto asset holders, security-focused users
* **GitHub Repository:** https://github.com/Ahmetcemil1/legacy-vault

## 1. Project Description

Legacy Vault is a client-side zero-knowledge digital estate planning and inheritance platform. It bridges the gap between digital asset custody and inheritance law, allowing users to securely store sensitive digital credentials, passwords, medical records, and video messages, which are only released to designated beneficiaries upon death validation via a decentralized, multi-signature consensus protocol or certified death claim administrative verification.

The project is fully built with 100% cryptographic parity across its React Web and Flutter Mobile clients using 2048-bit RSA-OAEP asymmetric keypairs and Shamir's Secret Sharing (SSS) over Galois Field GF(256).

## 2. Value to the Filecoin Ecosystem

Legacy Vault requires a highly available, decentralized, and censorship-resistant storage layer to save users' client-side encrypted credentials, death claim documents, and large posthumous video messages without relying on centralized, vulnerable storage systems. 

By integrating **IPFS and Filecoin** (via Web3.Storage/Lighthouse), Legacy Vault will:
1. Bring significant, recurring transaction volume of encrypted digital estate payloads to the Filecoin Network.
2. Demonstrate a real-world, high-utility siber-security use case for decentralized archives.
3. Guarantee that even if our centralized metadata servers go down, users' encrypted inheritance archives remain permanently available and retrievable worldwide.

## 3. Cryptographic Implementation Details

* **Client-Side Symmetric Encryption:** Deterministic AES-256-CBC derived locally via SHA-256 of the master password, prepended with a cryptographically secure random 16-byte IV.
* **Client-Side Asymmetric Encryption:** Standard 2048-bit RSA-OAEP (SHA-256 digest) formatting SPKI (public key) and PKCS#8 (private key) Base64 ASN.1 DER structures.
* **Shamir's Secret Sharing (SSS):** Polynomial evaluation and Lagrange interpolation executed entirely client-side over Galois Field GF(256) (using primitive polynomial x^8 + x^4 + x^3 + x^2 + 1) to split the master password into k-of-n encrypted shares.

## 4. Road Map & Milestones

We are requesting **$15,000 USD** in funding to execute the IPFS/Filecoin integration layer:

### Milestone 1: IPFS Dynamic Encryption & Upload Integration
* **Deliverable:** Update React Web and Flutter Mobile clients to upload client-side encrypted payloads (documents, video messages) directly to IPFS using pinning services.
* **Timeframe:** 4 weeks
* **Funding Request:** $7,500 USD

### Milestone 2: Filecoin Decentralized Archiving & Backup Layer
* **Deliverable:** Implement automated Filecoin storage deals for permanent archiving of digital vaults, and integrate CID retrieval directly into the recovery dashboards.
* **Timeframe:** 4 weeks
* **Funding Request:** $7,500 USD

## 5. Team

* **Ahmet Cemil** - Lead Software Architect & Cryptographer (Solo Technical Founder). Developed the complete aligned React Web + Flutter Mobile cryptographic framework.