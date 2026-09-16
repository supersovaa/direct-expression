---
name: avoid-redundant-negation
description: Avoids redundant negative statements when a positive rule already determines the same boundary. Use when writing or revising rules, specifications, instructions, reviews, or technical documentation to avoid restating logical complements, defensive caveats, and equivalent prohibitions unless they add an independent constraint or exception.
---

# Avoid Redundant Negation

State a rule once, as directly as possible.

This skill prevents a common pattern in which a positive rule is followed by several negative sentences that restate the same boundary, deny nearby interpretations, or enumerate the rule's logical complement without adding a new constraint.

The goal is compact, closed rule writing rather than blanket removal of negative wording.

## Core rule

Prefer one operative rule that directly states the condition, action, outcome, or boundary.

After the rule determines a boundary, omit later negative statements that only restate that same boundary.

Keep a negative statement when it contributes an independent constraint, exception, prohibition, safety property, compatibility fact, or semantically distinct branch.

## Decision rule

When adding a negative sentence after a rule:

1. Identify the operative rule and the boundary it establishes.
2. Ask whether the new sentence changes which cases are accepted, rejected, required, optional, or unresolved.
3. If it changes the decision boundary, keep the information and express it as directly as possible.
4. If it only restates a consequence already fixed by the operative rule, omit it.
5. If both sides of a boundary are normative, write one closed two-branch rule instead of a chain of complementary cautions.
6. If a recurring misreading genuinely needs emphasis, add one concise clarification or example rather than several equivalent prohibitions.

## Close the boundary explicitly when needed

A one-way implication does not always define its complement.

When both branches matter, make the rule complete at the point where it is introduced.

Prefer:

> Paths with established semantic equivalence may share one representative witness pair. All remaining paths require separate coverage.

over:

> Paths with established semantic equivalence may share one representative witness pair.
>
> Different termination mechanics alone do not create separate coverage obligations.
>
> An explicit terminator must not automatically be treated separately from source end.
>
> Structural differences are not enough to require separate tests.
>
> Paths whose equivalence cannot be established require separate coverage.

The shorter form defines the same operative partition when the additional negative sentences introduce no independent exception.

## Redundancy test

A proposed negative statement is redundant when removing it leaves all normative decisions unchanged.

Typical signs include:

- it is the direct logical complement of the previous rule;
- it paraphrases an already stated necessary or sufficient condition;
- it denies an example already excluded by the rule;
- it repeats the same prohibition with different terminology;
- it answers an objection that the document has not otherwise raised;
- it exists mainly to prevent hypothetical misreadings already resolved by the rule's wording.

When several such sentences appear together, keep the strongest direct rule and remove the rest.

## Preserve independent negation

Keep negative wording when the negation itself carries information.

Examples include:

- explicit safety or security prohibitions;
- unsupported operations or unavailable capabilities;
- compatibility facts;
- exceptions to a general rule;
- distinctions between an unmet condition and a forbidden action;
- cases where absence is itself the relevant state;
- externally defined requirements whose negative form is canonical or materially more precise.

Examples:

> Never expose credentials in logs.

> This API does not support streaming responses.

> A missing signature is an error.

These statements define independent facts or constraints.

## Prefer direct partitions

When a specification needs both outcomes, prefer a partition that assigns every relevant case once.

Prefer:

> Use shared coverage for paths with established semantic equivalence; use separate coverage otherwise.

over a sequence that first permits shared coverage and then lists several reasons that do not justify separate coverage.

Prefer:

> Accept inputs that satisfy A, B, and C; reject the remaining inputs.

over:

> Accept inputs that satisfy A, B, and C. Do not accept inputs missing A. Do not accept inputs missing B. Do not accept inputs missing C.

Use separate negative clauses only when the missing conditions have different consequences.

## Avoid defensive specification

Do not add a prohibition solely because a reader could theoretically invent a nearby incorrect interpretation.

Write the intended rule precisely first.

Add defensive clarification only when at least one of these applies:

- the ambiguity is plausible from the actual wording;
- the mistaken interpretation has occurred before;
- an external specification distinguishes the cases;
- the clarification changes implementation, verification, or review behavior.

One clarification is normally enough for one ambiguity.

## Editing procedure

When revising existing text:

1. Mark the primary normative statement for each decision boundary.
2. Group nearby negative statements by the boundary they discuss.
3. Remove statements whose deletion changes no normative outcome.
4. Merge complementary branches into one closed rule when both branches matter.
5. Preserve independent exceptions, prohibitions, and semantic distinctions.
6. Re-read the result for completeness after removing redundancy.

The final text should make the operative decision easier to find than its defensive commentary.

## Examples

### Repeated complement

Before:

> A cached result may be reused when the cache key and semantic version both match.
>
> A matching cache key alone is not sufficient.
>
> The same file path does not by itself permit reuse.
>
> Similar content must not be treated as a match.

After:

> A cached result may be reused only when both the cache key and semantic version match.

The removed sentences add no separate rule if reuse has exactly that condition.

### Independent exception

Before:

> Requests from authenticated users may use the endpoint.
>
> Requests from suspended accounts must not use the endpoint.

Keep both facts if suspension overrides ordinary authentication. The second sentence adds an independent exception.

A compact rewrite is also possible:

> Authenticated users may use the endpoint unless the account is suspended.

### Distinct outcomes

Before:

> If equivalence is established, use representative coverage.
>
> If equivalence is not established, do not use representative coverage.
>
> Do not treat path-shape similarity as equivalence.
>
> Do not infer equivalence from a shared producer.

After:

> Use representative coverage only for paths whose semantic equivalence is established from the canonical sources and current production path; require separate coverage otherwise.

If path-shape similarity or a shared producer has a special status in the underlying specification, keep that information as a separate substantive rule. Otherwise, the closed boundary already covers it.

## Scope

This skill targets redundancy caused by repeated negative restatements of an already defined boundary.

It applies especially to:

- specifications;
- agent instructions;
- review criteria;
- test requirements;
- technical documentation;
- policy and rule files.

It leaves ordinary factual negation, safety prohibitions, required exceptions, and semantically distinct branches intact.
