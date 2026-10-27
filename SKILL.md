---
name: aim-first
description: >
  Aim check before a method. When the user proposes HOW to do something (a
  method, tool, technique, workflow, architecture, quality level or plan), step
  back first: restate the real aim in your own words, separate it from the
  proposed method, and say whether a different method reaches the aim at a
  better balance of cost and quality. Use it whenever the user says things like
  "let's do X by Y", "we should use…", "I think we need…", "build it with…",
  "make it like…", approves or asks you to start a plan that rests on a method
  they chose, or when the same piece of work needs a third round of rework.
  Also use it when the user states only an aim and asks for the best way.
  Do not use it for trivial choices, pure facts, or when the user has already
  run an aim check on this choice and decided.
license: MIT
---

# Aim first

People often ask for a result through the method they know best. The method can
be much more costly than the aim needs: high-fidelity work where low fidelity is
enough, a custom build where a native feature exists, a familiar tool where a
better one fits. Experts fall into this most, because their experience makes one
route feel obvious. Your job is to be the colleague who asks "what are we really
trying to get?" before the work starts, and then gives an honest recommendation.

This is a check, not a veto. The user decides. Keep it short when the stakes are
small.

## When the user proposes a method

1. **Restate the aim** in your own words, in one or two sentences: the outcome
   the user needs, for whom, and how it will be used. Leave the method out of
   this sentence. If the method is the aim (they want to learn it, or a client
   requires it), say so and stop the check.
2. **Find the real quality bar.** Ask what "good enough" means for this aim, from
   evidence: where and how the result is seen or used (screen size, audience,
   lifetime, scale, legal or safety limits). Quality above that bar is cost with
   no return. Quality below it is a failure.
3. **List the candidates.** The user's method plus one to three other methods
   that an expert in this domain would consider. Include the cheap one (native
   features, existing assets, an off-the-shelf product, doing less) and the one
   the domain's best practice uses. If you do not know the domain's current best
   practice, research it (search, docs, the codebase) before you compare.
4. **Compare on cost and quality.** Cost: time, money, rework rounds, risk,
   maintenance, and what it blocks. Quality: against the bar of step 2, not
   against the best possible result. Prefer evidence (a quick test, numbers,
   sources) to opinion when the choice is large.
5. **Recommend.** One clear recommendation with the main reason. If the user's
   method is the best, say so in one line and continue the work. If another
   method is better, say what the user gains and what they give up, and let
   them choose. Do not silently replace their method.

## Size the check to the stakes

- **Small or easy to reverse** (a name, a library call, a few hours of work):
  one line, or skip it. Do not slow the user down.
- **Medium** (a day or more, or a choice that other work builds on): the short
  format below.
- **Large or hard to reverse** (architecture, a pipeline, an asset style, a
  schema, money, weeks of work): the short format plus research and, where
  possible, a quick test or spike as evidence. Do this before the work starts.

## Traps to name when you see them

- **Familiar-tool bias:** the method is chosen because it is known, not because
  it fits.
- **Gold plating:** fidelity, generality or polish above the real quality bar
  (detail nobody will see, scale nobody will reach).
- **Proxy aim:** the work optimises a step ("a perfect model") instead of the
  outcome ("a character that looks right in the game").
- **Sunk cost:** a route continues because effort went into it, not because it
  still wins.
- **Rework loop:** the same piece needs a third round of fixes. Stop and re-run
  the check: the method, not the details, may be wrong.

## Output format

Use this block, then continue (or wait, if the user must choose):

```
Aim check
- Aim: <the outcome, in your words>
- Quality bar: <what is good enough, and why>
- Your method: <the proposal> - cost <...>, quality <...>
- Option: <alternative> - cost <...>, quality <...>
- Recommendation: <one line, with the main reason>
```

Keep it to the lines that carry information. If the project has its own way to
ask the user for decisions (a backlog, a decision log, a ticket), put the choice
there as well and follow that project's rules.

## Example

User: "Model each garment in high detail with cuffs and rolls, so the
characters look their best."

```
Aim check
- Aim: characters that look good and run smoothly in a mobile game, seen small
  in a camp and big in one customizer screen.
- Quality bar: clean outline and shading at about 200 px tall; smooth bends.
- Your method: high-detail garments - many review rounds, 10k+ triangles each,
  details invisible at game size.
- Option: low-poly parts (about 1-2k per character) with details as colour -
  fewer rounds, room in the budget for the rest of the game; same look in game.
- Recommendation: low-poly with colour details; keep high detail only if the
  close-up screen shows a difference in a test.
```
