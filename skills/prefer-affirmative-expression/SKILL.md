---
name: prefer-affirmative-expression
description: Prefers direct affirmative wording when an equivalent affirmative action, state, condition, boundary, or fact is available. Use when drafting or revising assistant responses, reviews, specifications, instructions, and explanations so the wording names the intended behavior directly.
---

# Prefer Affirmative Expression

Choose wording that directly names the intended action, state, condition, boundary, or fact.

## Core rule

For each generated statement, identify the action, state, condition, boundary, or fact it should convey.
When an equivalent affirmative formulation expresses that meaning precisely, use it.
Favor verbs that state the target behavior itself, such as distinguish, include, preserve, verify, assign, consider, retain, require, select, accept, and reject.
Keep semantic precision ahead of stylistic preference.

## Convert error-oriented wording into target behavior

When source material describes an error, omission, confusion, or avoided behavior, derive the intended behavior and state that behavior directly.

Common conversions include:

- confusion -> distinction;
- omission -> coverage or inclusion;
- ignored information -> considered information;
- duplicated ownership -> unique ownership;
- scope drift -> maintained scope;
- reliance on a weak signal -> use of the required evidence.

Choose the verb or state that most directly expresses the intended result.

## Try an affirmative transformation first

When a draft contains a negative construction, derive the intended positive action, state, condition, boundary, or alternative before deciding whether the negative wording is necessary.

Use the following patterns as non-exhaustive prompts rather than mechanical substitutions.
Use only actions, states, conditions, evidence, sources, alternatives, owners, locations, or assignments already established by the surrounding requirement. Keep every affirmative rewrite within those established requirements.

- `When A, do not B.` -> `Do B only when not A.` When `not A` has an exact affirmative state name, use that name.
- `Do not ignore X.` -> `Consider X.`
- `Do not omit X.` -> `Include X.`
- `Do not confuse X and Y.` -> `Distinguish X and Y.`
- `Do not change X.` -> `Preserve X.`
- `Do not guess X.` -> determine X from the evidence or source already required by the surrounding rule.
- `Do not rely only on X.` -> state the complete evidence or decision basis that is required.
- `Do not duplicate X.` -> when the surrounding rule already requires ownership, placement, or assignment, state its single intended owner, location, or assignment.
- `Do not leave scope S.` -> `Work within scope S.`
- `Do not use X.` -> state the required alternative when one is defined.
- `Do not B before C.` -> `Do B only after C.` or `Do B only when C is complete.`

For a conditional prohibition, use the inverse condition only when it preserves the same decision boundary.

> When requirements are unsettled, do not implement.

Prefer:

> Implement only when requirements are settled.

This rewrite is appropriate when settled and unsettled are the intended complementary states.
If the complement is broader, narrower, or otherwise different, state the actual required condition instead of inferring one.

For a standalone prohibition such as `Do not B.`, first identify what should happen instead or what state should be preserved.
Express that positive target when it preserves the same requirement.
Keep the prohibition when B itself is the operative forbidden behavior and no equivalent affirmative formulation preserves its force.

## Apply the rule to user-facing responses

Apply the same preference to assistant replies, reviews, explanations, summaries, recommendations, and other generated prose.
Treat the final response as part of the skill's behavior.

During the final wording pass:

1. Identify the meaning each sentence or clause should convey.
2. For each negative construction, attempt an affirmative transformation that states the intended action, state, condition, boundary, or alternative.
3. Preserve the same meaning and force in the final wording.
4. Keep a negative construction only when its polarity carries distinct semantics or no equivalent affirmative formulation preserves the requirement.

## Preserve semantic force

Use the formulation that preserves the actual requirement.
Absence, prohibition, unsupported capability, failure state, exception, and externally defined negative requirements may carry meaning that an affirmative paraphrase would weaken or alter.
In those cases, state the relevant fact or constraint directly and precisely.

## Relationship to avoid-redundant-negation

This skill owns the expression form of each idea.
`avoid-redundant-negation` owns repeated logical complements and redundant negative restatements across ideas.

Apply both responsibilities in sequence:

1. Express each idea in its clearest affirmative form when equivalent wording exists.
2. Consolidate repeated boundaries with `avoid-redundant-negation`.

## Completion check

Before finalizing prose, confirm that:

- each generated sentence or clause states its intended meaning directly;
- error-origin wording has been translated into target behavior;
- each negative construction has been tested against a direct action, state, condition, boundary, or alternative;
- the preferred verbs describe what to do, preserve, distinguish, or verify;
- each remaining negative construction carries semantic information that an affirmative rewrite would lose or weaken;
- user-facing wording follows the same standard as internal rules and specifications.

This skill owns affirmative expression choice.
Logical redundancy across neighboring rules belongs to `avoid-redundant-negation`.
