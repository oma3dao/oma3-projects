# IWPS — Inter World Portaling System

## The Problem: Walled Gardens

Virtual worlds, games, and spatial applications exist as isolated silos. Users cannot move between them — taking their identity, assets, or context with them. Every platform is a dead end. There's no equivalent of the hyperlink for 3D environments.

This fragments the user experience, locks creators into single platforms, and prevents the kind of network effects that made the open web successful.

## What IWPS Does

The Inter World Portaling System is a foundational API specification that enables seamless interoperability between diverse virtual worlds, applications, and platforms. It defines a standard protocol for teleportation — moving a user (and optionally their assets, identity, and preferences) from one virtual world to another.

IWPS works across fundamentally different architectures: traditional cloud infrastructure, blockchain-based networks, and hybrid combinations of both.

## How It Works

A teleportation is executed via two API calls:

1. **Query** — The source world contacts the destination to negotiate parameters: Can this user teleport? What assets are allowed? What's the landing location? What communication path should be used?

2. **Teleport** — The source world initiates the actual transfer. The destination launches its client, the user logs in, assets are moved, and both sides confirm completion.

```
┌────────────────┐          ┌────────────────┐           ┌────────────────┐
│  Source World  │──Query──▶│  Destination   │           │  Destination   │
│  (Client +     │          │  Cloud         │──Launch──▶│  Client        │
│   Cloud)       │─Teleport▶│                │           │                │
└────────────────┘          └────────────────┘           └────────────────┘
```

The protocol supports multiple communication paths depending on the environment — direct device-to-device, cloud-mediated, hybrid, and user-agent intermediated (for privacy).

## Key Capabilities

**Dynamic Teleportation** — Users move seamlessly between worlds on the same device or across multiple devices. The protocol negotiates the most secure and efficient communication path automatically.

**Flexible Identity** — Supports traditional usernames, email addresses, blockchain addresses, and passkeys. Identity can be verified separately by each world, passed through from the source, or mediated by a user agent.

**Asset Transfer** — Digital assets (avatars, items, characteristics) can be transferred between worlds with protocol-level negotiation of what's allowed and how assets should be adapted.

**Look and Feel Negotiation** — Worlds can negotiate discrepancies (e.g., what happens when a sci-fi weapon enters a medieval world) at the protocol level rather than through ad-hoc rules.

**Security Profiles** — Three levels from basic internet security (TLS) through OMA3's hardened certification program with mutual authentication, authorized CAs, and mandatory two-factor user login.

**Privacy via User Agents** — Users can optionally route teleportation through a trusted intermediary that prevents source and destination worlds from directly tracking movement patterns.

## Status

Approved OMA3 standard. [Base specification](https://github.com/oma3dao/iwps-specification) ratified (Draft). Extension frameworks for asset transfer, look-and-feel negotiation, and payments are in development.

## What Members Get

- Working group participation and voting rights on extension frameworks and specification changes 
- Contributor recognition under OMA3 governance processes ([details](./README.md#why-contribute))

---

Full specifications and working group access are available to OMA3 members. **[Join OMA3](https://www.oma3.org/join)**
