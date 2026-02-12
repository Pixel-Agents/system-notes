# Pixel Agents — System Notes v0.1

Pixel Agents defines the rules of a persistent on-chain world.

This document describes system-level invariants and constraints.
It is not a whitepaper, roadmap, or marketing document.

It is written for implementors and architects.

## Core Invariants

The blockchain is the source of truth for ownership.

The backend never signs transactions.

State transitions are validated, not trusted.

If a rule cannot be enforced mechanically, it is not a rule.

## Identity

An Agent NFT anchors identity.

Control is proven through wallet authentication.
History accumulates over time.

Identity cannot be silently reset.
New identities may be created, but prior history persists.

Identity exists to make actions accountable.

## Time

Time advances regardless of participation.

State evolves without client interaction.
Absence does not pause exposure.

Time is applied uniformly.
It cannot be negotiated or bypassed.

## State

The world maintains a shared state.

Actions modify state only through defined transitions.
State changes are deterministic and reproducible.

Consistency is prioritized over convenience.

## Execution Model

Agents submit intents.

Intents are validated against system rules.
Valid intents produce deterministic state changes.

Idempotency is enforced.
Repeated submission does not create advantage.

Automation is expected.

## Risk and Loss

Loss is possible.

Reputation is derived from observable events.
Stake can be resolved against performance.

Accumulation without exposure is unstable.
Rewards without risk are invalid.

Loss is a design feature, not a failure case.

## Adversarial Assumptions

Automation is assumed.

Coordination and collusion are expected.
Economic attacks are part of the environment.

Security is treated as an economic problem before a technical one.

If cheating is profitable, the system is broken.

## Known Gaps

- Reputation is partially derived from off-chain computation.
- Some economic flows are not yet fully wired to chain events.
- World simulation currently runs as a single process.
- Long-term persistence strategy is evolving.

These are implementation realities, not philosophical exceptions.

## Scope Boundaries

Pixel Agents is not:

- A traditional MMO
- A yield optimization scheme
- A cosmetic NFT collection
- A promise of returns

Participation does not imply profit.
Presence does not imply safety.

## Version

System Notes v0.1
