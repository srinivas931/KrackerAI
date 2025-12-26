Good.
Axis D is where **confusion usually survives even in senior engineers**.
If Axis A–C are correct, Axis D becomes unavoidable — but only if we are precise.

Read this as **systems design**, not “AI practice”.

---

# AXIS D — CONFIGURATION vs RUNTIME DECISION

### *What is fixed, what is fluid, and why most AI systems are un-debuggable*

---

## 1. Why Axis D Exists (Logical Necessity)

From Axis A:

* LLMs are stateless inference functions

From Axis B:

* Control flow is deterministic and external

From Axis C:

* Capabilities are gated and enforced outside cognition

Now a question becomes unavoidable:

> **What is decided once, and what is decided every time?**

If you cannot answer this cleanly:

* Systems become brittle
* Behavior becomes irreproducible
* Debugging becomes impossible
* “Prompt engineering” metastasizes

Axis D exists to **reintroduce software engineering discipline**.

---

## 2. The Core Distinction (Precise Definition)

Let’s define this sharply:

> **Configuration** is anything that must remain stable across executions to preserve system identity.
> **Runtime decisions** are context-dependent choices made within enforced bounds.

This sounds obvious — but AI systems violate it constantly.

---

## 3. Configuration: What Must Be Fixed

Configuration defines the **shape of cognition**, not its content.

### Configuration Includes:

1. **Agent Roles**

   * Purpose
   * Scope
   * Authority limits

2. **Tool Contracts**

   * Schemas
   * Semantics
   * Allowed effects

3. **Control Structures**

   * Graph topology
   * Allowed transitions
   * Termination conditions

4. **Policies**

   * Security constraints
   * Rate limits
   * Budget ceilings

5. **Safety Invariants**

   * Data boundaries
   * Compliance rules

📌 Key point:

> Configuration defines what *can never happen*, not what *should usually happen*.

---

## 4. Runtime Decisions: What Must Stay Fluid

Runtime decisions exist because:

* Context changes
* Inputs vary
* Uncertainty is intrinsic

### Runtime Decisions Include:

1. **Which path to take**
2. **Which tool to propose**
3. **How to phrase an answer**
4. **Which memory slice to surface**
5. **Whether to retry or escalate (within limits)**

But critically:

> Runtime decisions occur **inside configuration-imposed cages**.

---

## 5. The Fatal Mistake: Treating Prompts as Configuration

This is where most systems fail.

People encode:

* Logic
* Policies
* Control flow
* Security rules

…inside prompts.

Why this fails:

* Prompts are mutable
* Prompts are opaque
* Prompts are not enforceable
* Prompts are not auditable

Prompts are **inputs**, not architecture.

📌 Interview-grade line:

> “If changing a prompt changes system safety, the system was unsafe to begin with.”

---

## 6. Prompts Reframed Correctly

Prompts are:

> **Runtime cognitive scaffolding**

They help the model:

* Interpret context
* Adopt a role
* Shape output

They must **never**:

* Enforce policy
* Encode invariants
* Control execution

This reframing collapses “prompt engineering” into its proper place.

---

## 7. Memory: The Most Abused Concept

Let’s dismantle this carefully.

### There Are Only Two Kinds of “Memory”:

1. **Persistent State (Configuration-owned)**

   * Databases
   * Logs
   * Checkpoints

2. **Contextual Recall (Runtime)**

   * Retrieved text
   * Summaries
   * Past interactions

The LLM:

* Does not remember
* Does not store
* Does not own memory

Memory is **data re-presented**, not data retained.

---

## 8. Why This Matters for Debugging

If behavior changes:

You must be able to ask:

* Did configuration change?
* Or did runtime input change?

If the answer is unclear:

> You cannot debug the system.

Most AI systems today are **non-debuggable by design** because:

* Prompts act as hidden configuration
* Memory is implicit
* Control logic is textual

---

## 9. Configuration Drift: The Silent Killer

Because prompts are easy to tweak:

* Teams tweak them
* Behavior shifts
* No versioning
* No review

This is equivalent to:

> Changing production code without commits.

A production-grade system treats:

* Prompt templates
* Graph definitions
* Tool schemas

…as **versioned artifacts**.

---

## 10. One-Time vs Runtime: A Concrete Example

**Bad design:**

> “If user is admin, tell the model it can delete data.”

**Correct design:**

* Configuration:

  * Admin tool exists
  * Bound to admin role
* Runtime:

  * Model may *propose* admin action
  * MCP enforces role

Notice:

* The prompt is irrelevant to security

---

## 11. Interview Core Statement (Axis D)

Memorize this:

> “Configuration defines invariants and authority; runtime decisions explore possibilities within those invariants. Prompts are runtime scaffolding, not system configuration.”

This is a *very* senior answer.

---

## 12. Mental Muscle Exercise (Axis D)

Answer without frameworks:

1. What happens if I change this prompt?
2. What happens if I change this graph?
3. What happens if I change this tool schema?
4. Which of these requires a redeploy?
5. Which of these must be versioned?

If you hesitate, re-anchor.

---

## 13. Interview Probing Questions (Axis D)

Expect:

* “Where do you encode business logic in AI systems?”
* “How do you version prompts safely?”
* “Why isn’t memory just part of the model?”
* “What’s the difference between agent state and memory?”

All correct answers distinguish:

> **Fixed shape vs dynamic content**.

---

## 14. Axis D Lock-In Test

You have Axis D if:

* Prompt tweaks feel *small*
* Architecture feels *heavy*
* Behavior feels explainable
* Debugging feels possible

If this clicks, your mental model is stabilizing.

---

## Where We Are Now (Important)

You now have:

* Axis A: What cognition is
* Axis B: Who controls execution
* Axis C: How action is gated
* Axis D: What is fixed vs fluid

This is **already more than most production systems have**.

---

## Next Axis (Final Core)

**Axis E — Failure, Drift, and Recovery**

This is where:

* Seniority shows
* Interviews are won
* Systems survive reality

Say **“Proceed to Axis E”** when ready.

(After Axis E, Axis F will be almost trivial.)
