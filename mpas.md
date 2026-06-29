# MPAS — Multi-Party Action Standard

## The Problem: Unilateral Authority

Consequential actions in digital systems are authorized by single credentials — one token, one key, one session. If that credential is compromised, there's nothing between access and execution.

This isn't hypothetical. Major breaches happen because an attacker gains access to a developer's machine holding super-admin credentials for pull requests, database decryption keys, or cloud infrastructure. The credential alone is sufficient to act. There's no second check.

## The First Target: Agent Governance

AI agents are being connected to real systems — databases, code repositories, cloud infrastructure, payment services, customer data. But once an agent has credentials, there's nothing between it and execution. One compromised agent, one hallucinated decision, one prompt injection — and the action is done.

MPAS's first execution profile targets MCP directly. Any MCP-connected tool — GitHub, databases, cloud services, deployment pipelines — can be governed by MPAS via drop-in replacement servers that agents use transparently.

The agent proposes an action. Other agents, humans, or automated systems approve or reject. Only when policy is satisfied does the action execute. The agent's workflow is unchanged — it just calls tools as normal — but the system ensures nothing consequential happens without independent verification.

**Not every action requires approval.** Users define which actions require multi-party authorization and which can proceed freely. Read operations, low-risk queries, and routine tasks flow through without friction. Only the actions you designate — destructive operations, financial transactions, production deployments, sensitive data access — trigger the approval workflow.

## Web3 Proved the Pattern

Multi-sig wallets proved this works at scale: threshold approvals, cryptographic verification, separation of proposal from execution. Safe, smart contract wallets, and ERC standards demonstrated that requiring independent approvals before execution dramatically reduces the blast radius of any compromise.

But this capability is locked inside blockchain transaction signing. There's no equivalent standard for Web2 API calls, deployments, agent tool use, file operations, or cross-system actions.

OAuth — the most widely used authorization standard — still gives a single principal unilateral credentials. Applications that want multi-approval must build and maintain their own custom systems.

## MPAS: Multi-Party Authorization for Any Action

The Multi-Party Action Standard generalizes the multi-sig primitive: **propose → collect approvals → verify threshold → execute**. It works for any action in any system — API calls, deployments, database operations, agent tool use, payments, infrastructure changes.

Key properties:

- **Cryptographic proof of each approval** — signed, verifiable, auditable
- **Rich policy model** — far beyond simple M-of-N thresholds (see below)
- **Protocol-neutral** — works across Web2, Web3, AI agents, cloud, and local applications
- **Portable approval artifacts** — applications and adapters use a common approval package rather than inventing custom approval flows
- **Selective enforcement** — only the actions you choose require approvals

## Policy: More Than Thresholds

MPAS policies go well beyond "3 of 5 approve." The current draft supports:

- **Role-based requirements** — require at least one human signer, or at least one signer from a specific team
- **Signer class diversity** — require approvals from both humans and agents, or from multiple organizations
- **Super-admin overrides** — designated principals can authorize actions unilaterally for emergency scenarios
- **Action-level granularity** — different actions have different policies (e.g., read = no approval, delete = 2 humans + 1 agent)
- **Contextual conditions** — policies that vary based on the action's parameters, target system, or risk level

This means organizations can model their actual governance — not just a flat vote, but the nuanced decision-making structures they already use.

## Protocol Roles

```
┌──────────┐     ┌───────────────┐     ┌─────────┐     ┌──────────┐     ┌─────────────┐
│ Proposer │────▶│ Coordination  │────▶│ Signers │────▶│ Verifier │────▶│ Application │
└──────────┘     └───────────────┘     └─────────┘     └──────────┘     └─────────────┘
   Initiates        Routes proposal       Review &        Checks policy     Executes the
   the action       to eligible           approve or      satisfaction      approved action
                    signers               reject
```

- **Proposer** — initiates an action, constructs the proposal, produces the first approval
- **Signer** — reviews and cryptographically approves (or rejects) a proposed action
- **Verifier** — determines whether collected approvals satisfy policy before execution
- **Application** — executes the approved action

These roles can be filled by humans, AI agents, devices, services, or organizations.

## The Credential Adapter Pattern

MPAS can be integrated natively into applications. But for immediate adoption, a **Credential Adapter** sits in front of existing applications without modifying them:

- Holds the real credentials (API keys, tokens, signing keys)
- Receives MPAS-verified action packages
- Only releases credentials or executes when policy is satisfied

No change to the downstream application is required when a trusted Credential Adapter can safely translate and execute the approved action. This means existing systems can be governed by MPAS today — the application doesn't need to know about MPAS at all.

## Relationship to Other Standards

**OMATrust** answers: *should this service or signer be trusted?* Reputation and attestations for MPAS components — signers, verifiers, coordination servers — live on OMATrust, so participants can verify trustworthiness before including them in approval workflows.

**x402** handles: *payment negotiation and proof.* When an action involves a payment, x402 negotiates the economic terms; MPAS governs whether the agent or user is authorized to perform that action in the first place.

**Agent runtime hooks** (e.g., tool-use interception in agent frameworks) can identify *where* a runtime should pause or evaluate an event. MPAS defines the cryptographic approval package and verification process for the *specific action* at that pause point.

## Use Cases

**AI agent governance** — Agents propose actions but cannot execute unilaterally. Other agents or humans must approve before anything consequential runs. The first implementation targets MCP tools.

**Compromised credentials** — Even with root access, a single credential isn't enough. The system won't execute without independent approvals from other parties.

**Operational security** — Deployments, database migrations, key rotations, destructive operations — all require multi-party sign-off without custom code.

**Cross-organization collaboration** — Multiple parties from different organizations approve a shared action with cryptographic proof.

**Regulatory compliance** — Auditable trail of who proposed, who approved, who rejected, what was executed — with cryptographic binding at every step.

## Status

Proposed standardization track. Initial technical design and draft specification contributed; pending OMA3 approval. MVP implementation in progress to validate the design.

Future execution profiles planned: OpenAPI operations, EVM transaction intents, GraphQL operations, HTTP requests, CLI commands.

## Links (private — member access only for now)

- **Canonical repository:** [github.com/oma3dao/mpas](https://github.com/oma3dao/mpas) — specifications, SDK, example implementation, application registry, and conformance tools
- **Draft specification:** [github.com/oma3dao/mpas/specs](https://github.com/oma3dao/mpas/tree/main/specs)

## What Members Get

- Full normative draft specifications (MPAS Core, HTTP Profile, Application Plugin Profile, Policy Profile)
- Canonical repository access (SDK, example implementation, conformance tools)
- Working group participation and voting rights on the standard
- Early access to implementations and integration support
- Contributor recognition under OMA3 governance processes ([details](./README.md#why-contribute))

---

Full specifications and working group access are available to OMA3 members. **[Join OMA3](https://www.oma3.org/join)**
