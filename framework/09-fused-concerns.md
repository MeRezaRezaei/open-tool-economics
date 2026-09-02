# The Fused-Concern Problem — Separating a Tool Stuck Inside Its Performance

## The problem, from the raw

> There are a lot of performance that are dependent on tools that are integrated
> into performance. The question is: how to separate those?

The raw names the difficulty directly, and gives the diagnostic law that probes it:

> If we decrease the tool from performance, the performance also degrades. But
> if we add tool, the performance evolves.

## Why the probe seems to fail here

Removing the fused tool degrades the performance — so it looks like the thing is
not a separate tool. That is expected, not evidence of failure.

The moment a tool is integrated into a performance, the act of removing it
damages the performance by construction. The probe appears to say "this is not a
tool, this is the performance itself." But that reading mistakes the coupling
for the identity. The degradation is the signature of a *fused* tool, not proof
that no tool exists.

## The method

1. Ask: does the *same* integration repeat across many performances?
2. If yes, the repeated pattern is NOT the performance — it is a hidden tool.
3. The thing to extract is the **integration pattern itself**: a layer that does
   the integrating, which performances attach/detach on demand.
4. Extract it, open it (framework/08 makes it durable), keep the remaining
   performance as the money gate.

The raw's own formula for making new tools confirms the target:

> how to make a new tool by separating performance from the pattern that the
> performance follows repeatedly.

## Worked example (auth integration)

State: every app fuses an auth sub-system into itself. Removing it degrades the
app (probe: yes). But the same auth integration repeats across every app. So the
integration pattern is the hidden tool. Extract it as an open auth layer; apps
detach their embedded auth and attach the open layer. The app (performance)
stays sellable; the auth integration (tool) becomes open.

## Where this lands in the loop

It is step 2 (SEPARATE) of `07-the-full-cycle.md` applied to the hardest case:
when you cannot pull the tool out, pull the pattern of integrating it out
instead.
