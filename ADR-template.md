---
# MADR 4.0 front matter, plus four fields added for Power Platform work (marked *).
status: "proposed | accepted | rejected | deprecated | superseded by ADR-NNNN"
date: YYYY-MM-DD  # when the record was last changed
decision-makers: role (name)  # the role outlives the person
consulted: role (name), role (name)
informed: role or group
confidence: "high | medium | low"  # * low is fine; say why in Context
scope: "tenant | environment group | environments: ... | solution: ..."  # *
review-triggers:  # * events that should make someone reread this record
  - "..."
related: ["ADR-NNNN"]  # *
---

# NNNN. {Decision in a few words, phrased as the outcome}

> **Summary:** In the context of {situation}, facing {concern}, we decided for {option} to achieve {quality}, accepting {downside}.

## Context and Problem Statement

{The question being decided, and the forces and constraints that applied at the time. Two to four sentences. Write it for someone who joins after everyone involved has left.}

## Considered Options

* {Option 1}
* {Option 2}
* {Option 3}

## Decision Outcome

Chosen option: "{Option N}", because {the reason it won, in one or two sentences}.

{Optional: the decision as a single active-voice sentence. "We will ..."}

### Assumptions

* {Something that must stay true for this decision to remain sound, and who protects it.}

### Consequences

* Good, because {...}
* Bad, because {...}  <!-- Write the ones you would rather not. -->
* Neutral, because {...}

### Confirmation

{How anyone can check the decision is being followed: a policy, a review step, a report. If nothing checks it, say so plainly.}

## Pros and Cons of the Options

### {Option 1}

* Good, because {...}
* Bad, because {...}

### {Option 2}

* Good, because {...}
* Bad, because {...}

## More Information

{Links to related records, source documents and evidence. The record must still make sense if every link breaks.}
