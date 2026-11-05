---
status: "proposed"
date: 2026-08-21
decision-makers: Governance framework owner
consulted: Platform architect, IT security lead, CoE team
informed: Copilot Studio makers
confidence: "medium"
scope: "tenant"
review-triggers:
  - "Reviewers report that the nine profiles are too complex to apply consistently"
  - "Microsoft's zoned governance guidance changes materially"
related: ["ADR-0010", "ADR-0012", "ADR-0013"]
---

# 0011. Govern agents on two independent axes: capability tier and maker zone

> **Summary:** In the context of governing agents built by everyone from citizen makers to professional developers, facing a choice between one governance scale and two, we decided to classify every agent on capability tier and maker zone separately, to achieve controls that fit both what an agent can do and who built it, accepting nine governance profiles instead of three.

## Context and Problem Statement

Agent creation is low-friction, so governance has to prevent agent sprawl without treating every agent as equally risky. Most published Copilot governance guidance uses a single scale. Microsoft's zoned governance guidance for Copilot Studio governs by who builds and how much oversight surrounds them (Zone 1 Citizen, Zone 2 Partnered, Zone 3 Professional), not by what the agent does.

What should Fabrikam's governance rules key off?

## Considered Options

* A single tier scale based on capability
* Microsoft's maker zones on their own
* Two independent axes: capability tier (ADR-0010) and maker zone

## Decision Outcome

Chosen option: "Two independent axes", because a single scale conflates what an agent can do with who is allowed to build it. A citizen developer with no coding background can still connect a flow that writes to a production system, and a professional developer can still build a read-only FAQ bot. A single scale either over-governs the simple case or under-governs the risky one.

The two axes cross to form a nine-cell matrix. Each cell sets the connector policy, approval path and monitoring level for agents in it.

### Assumptions

* Every agent can be placed in exactly one zone, because each zone has its own environments (ADR-0013).

### Consequences

* Good, because a pro developer's read-only bot is not forced through full compliance review, and a citizen's agent that writes to production cannot slip through as "low risk".
* Bad, because there are nine governance profiles to define, explain and maintain instead of three.
* Bad, because every agent needs two classifications at review, not one.
* Neutral, because this extends Microsoft's zoned model with a second axis that Microsoft's guidance does not include. Readers of Microsoft's guidance will find more here than they expect. The difference is deliberate.

### Confirmation

The publish review records both the tier and the zone. The framework owner samples reviews each quarter for consistency.

## Pros and Cons of the Options

### A single tier scale

* Good, because it is simple to explain and apply.
* Bad, because it ignores who built the agent, so maker skill and oversight have no effect on the controls.

### Maker zones on their own

* Good, because it follows Microsoft's published guidance directly.
* Bad, because it ignores what the agent can do. A Zone 2 chatbot and a Zone 2 autonomous agent would get the same controls.

## More Information

* Source: Fabrikam agent governance framework, Sections 1, 3 and 4.
* [Implement a zoned governance strategy, Copilot Studio guidance, Microsoft Learn](https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/sec-gov-phase2)
