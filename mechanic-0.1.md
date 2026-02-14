# Mechanic 0.1

This document defines the concrete mechanics for v0.1: intents, validation rules, state transitions, idempotency, and loss surface.
It does not define economic parameters, contract ABIs, or API schemas.

**Audience:** Implementors. Conforms to [System Notes v0.1](./README.md).

**Layer:** Agent execution; world simulation.

---

## Scope

Mechanic 0.1 covers the first set of actor-facing procedures: what can be submitted, how it is validated, and how state changes.
Mechanics must satisfy the invariants in System Notes (identity, time, state, execution model, risk).

No public execution endpoint is exposed.
Mechanics are specified; deployment is test environments only.

---

## Intents v0.1

| Intent | Status   |
|--------|----------|
| MOVE   | Specified   |
| MINE   | Specified   |
| Others | Undefined |

---

## Validation v0.1

An intent is valid only if:

- Identity is authenticated.
- Presence or eligibility is satisfied.
- Cooldown or time constraints are satisfied.
- Outcome is deterministic given intent and state.

Invalid intents must not modify state.

---

## State transitions

- `apply(intent, state) -> newState + events`
- Transition logic must be pure: no side effects in the transition itself.
- State changes must be deterministic and reproducible.

---

## Idempotency

- `intentId` must be unique per agent per window.
- Repeated submission of the same intent must not create advantage.
- Duplicate intentIds must be rejected or no-op.

---

## Loss surface

One primitive loss is in scope for v0.1: **fatigue / decay**.

- A fatigue or decay dimension applies to the agent (or to a relevant state handle).
- It advances over time or with activity according to a deterministic rule.
- It does not require token economics.
- It introduces exposure: absence or overuse can reduce capability or trigger a loss condition.
- The same rule applies to human and automated agents; no actor-specific decay.

Slash and item durability are not in scope for v0.1.

---

## Reference

- [System Notes v0.1](./README.md) — invariants, identity, time, state, execution model, risk, adversarial assumptions, known gaps, scope boundaries.
- Deterministic Simulation Standard (main repo `docs/DETERMINISTIC_SIMULATION_STANDARD.md`) — tick model, ordering, replay determinism, conflict handling.

---

## Version

Mechanic 0.1
