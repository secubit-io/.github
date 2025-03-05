# Secubit: <br><span style="font-weight:normal;">A Self-Sovereign Wallet-as-a-Service Platform with Bank-Grade Security</span>

## Abstract
Secubit is a **wallet-as-a-service (WaaS)** solution that combines **bank-grade Hardware Security Modules (HSMs)**, **distributed Multi-Party Computation (MPC) wallets**, and **self-sovereign key & policy management**. Our solution addresses institutional-grade security, regulatory compliance, and operational flexibility for crypto asset management.

## 1. Introduction
Traditional digital asset custody solutions face challenges in balancing **security, usability, and cost-effectiveness**. Secubit provides a **hybrid security model** that integrates:
- **HSM-backed key storage and policy execution**
- **Threshold-based multi-party approvals**
- **Self-sovereign custody and governance models**
  
Secubit aims to serve **institutional fund managers, treasury teams, and crypto exchanges.**

## 2. Architecture Overview
### System Entities
- **Secubit:** A platform for the custody and management of institutional crypto assets. It consists of:
    - **Secubit Webservice:** A dashboard for creating and manging self-sovereign wallets.
    - **Secubit HSM Network:** A network of tamper-proof HSM devices hosted in SOC-2 datacenters.
- **Client:** A fund/treasury management organization who uses Secubit.
- **Approvers:** A group of client agents who participate in an MPC protocol to authorize transaction signing.  
- **Third-Party Providers:** Offer services and resources used by the Secubit platform.
    - **Cloud Provider:** Hosts Secubit webservice and databases. E.g., *Amazon EC2*.
    - **Node Provider:** Blockchain node and analytics providers. E.g., *Alchemy, Moralis, 0xArc.*

### 2.1 Security Foundations
Secubit’s infrastructure relies on **FIPS 140-3 Level 3 HSMs** and state-of-the-art **MPC protocols**, ensuring:
- Tamper-resistant private key storage
- In-HSM transaction signing (keys never leave HSMs)
- In-HSM policy enforcement
- Client-driven threshold approvals

### 2.2 Key Management & Policies
Secubit provides flexible key custody models:
1. **Custodial Mode**: Keys are managed within the Secubit HSM network with in-HSM transacion signing and policy enforcements upon a sufficient number of signed approvals are receives from the client's agents.
2. **Non-Custodial Mode**: Client's agents hold signing key shares while leveraging HSMs for signing.

In both cases, key approvals are enforced using threshold signatures, where multiple approval keys must sign before any transaction is signed.

## 3. Transaction Flow

### 3.1 Custodial Wallet Model
1. Client submits a transaction via the **Secubit API**.
2. The transaction is verified against **predefined policies** inside the HSM.
3. If approved, the HSM signs the transaction and broadcasts it to the network.

### 3.2 Non-Custodial Wallet Model
1. Client holds a **partial key share**.
2. Secubit HSM holds the **other key share** and enforces **policy-based approval**.
3. Transactions require multiple authorized signers to proceed.

### 3.3 Efficient Key/Policy Storage 
@CKV8nnFjTZKBO2dRO_vLWg describe the Merkle tree algorithm.

## 4. Integration & APIs
Secubit provides **developer-friendly APIs** for seamless integration into existing systems:
- **Universal Passkey Support** for authentication
- **Metamask & WalletConnect support**
- **RESTful APIs & SDKs** for transaction execution, policy configuration, and monitoring

For more information, visit [Secubit Website](secubit.io) or contact us at [moreinfo@secubit.io](mailto:moreinfo@secubit.io).
