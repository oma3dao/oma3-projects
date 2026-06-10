# OMATrust — Verification Protocol for the Open Internet

## The Problem: No Universal Trust Layer

The open internet was never designed with a way to verify legitimacy. SSL certificates prove domain ownership but not safety. Audits live in PDFs that can't be verified programmatically. Reputation is siloed inside walled gardens — App Store ratings don't help you evaluate a website, and Amazon reviews don't help you assess an API.

Inside platforms like Apple, Google Play, or Roblox, trust systems work and users rely on them. But these systems are closed and proprietary. The vast majority of the internet — websites, APIs, SaaS tools, smart contracts — has no equivalent.

As AI agents begin transacting at machine speed and scale, this gap becomes a systemic risk. Agents should not pause to read reviews on a forum. They need programmatic, cryptographic, real-time trust signals — and those don't exist today.

## What OMATrust Does

OMATrust makes trust a machine-verifiable primitive. It replaces unverifiable badges, PDFs, and siloed reviews with cryptographic proofs that anyone — human or AI agent — can query in real time.

The architecture has two integrated layers:

**OMATrust** — a cross-chain verification protocol where anyone can publish provable cryptographic attestations on any internet service, and where humans and machines can verify legitimacy before engaging.

**OMAChain** — an Ethereum Layer 2 that hosts canonical coordination contracts, tracks cross-chain data, subsidizes gas for end users, and provides decentralized indexing.

## Core Capabilities

**Identity Registry** — Apps, APIs, websites, and services are tokenized as onchain assets (NFTs), giving each a persistent, verifiable identity that can be referenced across chains. Compatible with emerging standards like Ethereum's ERC-8004.

**Attestation Framework** — Anyone can publish cryptographic attestations: security audits, compliance certifications (GDPR, SOC2, ISO 27001), user reviews, and identity bindings. Attestations are tamper-resistant, interoperable, and queryable.

**Verification Flow** — Clients, users, and AI agents derive a DID from a URL or contract address, query coordination contracts, collect attestations, and make trust decisions — all programmatically, in real time.

**Cross-Chain** — OMATrust functions across multiple blockchains. OMAChain's coordination contracts track attestations and prevent duplicate tokenization globally.

**Gas Subsidization** — User-facing trust operations like reviews are free. OMAChain subsidizes these writes so adoption isn't gated by crypto knowledge or wallet balances.

## Use Cases

**AI agents** — Before calling an API or sending a micropayment, agents query OMATrust to verify the service is legitimate, audited, and compliant. This prevents fraud at machine scale.

**x402 micropayments** — The x402 protocol (internet-native micropayments backed by Coinbase, Google, and Cloudflare) has integrated signed offers and receipts as extensions that map directly into OMATrust attestations. When every API call involves a payment, verifying the service before paying becomes non-negotiable. OMATrust provides that verification layer.

**MPAS component reputation** — The Multi-Party Action Standard relies on signers, verifiers, and coordination servers. OMATrust provides the reputation and attestation layer for these components — allowing participants to verify the trustworthiness of signers and services before including them in approval workflows.

**End users** — Verifiable reviews and certifications are visible before downloading an app or trusting a website — app-store-level trust, but for the open internet.

**Auditors and certifiers** — Security firms publish proofs directly onchain instead of as unverifiable PDFs. Attestations are cryptographic, machine-readable, and persistent.

**Developers** — Tokenize software once, gain global discoverability. Reputation travels with the app across ecosystems without per-marketplace re-registration.

**Enterprises** — Compliance certifications (HIPAA, SOC2, GDPR) become cryptographically verifiable, enabling automated trust decisions in regulated integrations.

## Governance

OMA3 is a Swiss non-profit association (Verein) with no owners and no equity. Governance follows one-member-one-vote. No single company, investor, or group of insiders can capture the protocol. This credible neutrality is what allows competitors to cooperate on shared trust infrastructure.

## Status

Accepted as an OMA3 standards effort. The specification is undergoing active revision and has not yet been ratified. An MVP implementation is complete — including OMAChain testnet, OMATrust contracts, and identity registry — and is being used to validate the design.

## Links

- **Website:** [omatrust.org](https://omatrust.org)
- **Draft specification:** [github.com/oma3dao/omatrust-docs](https://github.com/oma3dao/omatrust-docs)

## What Members Get

- Working group participation and voting rights on the standard
- Early access to testnet, contracts, and integration support
- Contributor recognition under OMA3 governance processes ([details](./README.md#why-contribute))

---

Full specifications, whitepaper, and working group access are available to OMA3 members. **[Join OMA3](https://www.oma3.org/join)**
