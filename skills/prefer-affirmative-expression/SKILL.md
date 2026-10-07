---
name: prefer-affirmative-expression
description: Prefers direct affirmative wording when an equivalent affirmative action, state, condition, boundary, or fact is available. Use when drafting or revising assistant responses, reviews, specifications, instructions, and explanations so the wording names the intended behavior directly.
---

# Prefer Affirmative Expression

Choose wording that directly names the intended action, state, condition, or boundary.

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

## Apply the rule to user-facing responses

Apply the same preference to assistant replies, reviews, explanations, summaries, recommendations, and other generated prose.
Treat the final response as part of the skill's behavior.

During the final wording pass:

1. Identify the meaning each sentence or clause should convey.
2. Choose the direct affirmative action, state, condition, boundary, or fact that expresses that meaning.
3. Preserve the same meaning and force in the final wording.
4. Keep a negative construction when its polarity carries distinct semantics.

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
- the preferred verbs describe what to do, preserve, distinguish, or verify;
- each remaining negative construction adds semantic information;
- user-facing wording follows the same standard as internal rules and specifications.

This skill owns affirmative expression choice.
Logical redundancy across neighboring rules belongs to `avoid-redundant-negation`.
