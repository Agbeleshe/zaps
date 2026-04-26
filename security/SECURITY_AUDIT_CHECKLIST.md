# Security Audit Checklist for External Auditors

This document outlines the specific areas of the Zaps architecture that require comprehensive penetration testing and auditing prior to Mainnet launch.

## 1. Smart Contracts (`/contracts`)
- [ ] Reentrancy attacks check on escrow and payment router contracts.
- [ ] Logic flaws in `reputation_score_contract`.
- [ ] Upgradability pattern security (Proxy contract vulnerability checks).
- [ ] Access control checks (Are admin privileges overly broad?).
- [ ] Overflow/Underflow (if applicable to the specific Rust/CosmWasm versions).
- [ ] Oracle manipulation testing for merchant conversion rates.

## 2. Backend Infrastructure (`/backend`)
- [ ] Authentication and JWT token validation testing.
- [ ] Rate limiting effectiveness (DDoS mitigation on `/api/v1/auth`).
- [ ] SQL Injection / NoSQL Injection checks on merchant databases.
- [ ] Insecure Direct Object References (IDOR) on transaction histories.
- [ ] TLS configuration and cipher suite review.

## 3. Mobile Application (`/mobileapp`)
- [ ] Secure storage of private keys (iOS Secure Enclave, Android Keystore).
- [ ] Deep link hijacking vulnerabilities.
- [ ] Code obfuscation and reverse engineering resistance.
- [ ] SSL Pinning verification.

## 4. Key Management & Operations
- [ ] Cold storage vs Hot wallet separation procedures.
- [ ] Multi-sig configuration for treasury and admin keys.
- [ ] CI/CD pipeline security (GitHub Actions secret scoping).
