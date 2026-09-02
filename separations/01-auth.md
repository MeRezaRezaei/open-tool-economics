# Separation 1 — Auth as an open layer

## The repeated pattern

Every application fuses an auth sub-system into itself — sign-up, login, sessions,
password reset, roles, permissions. The same integration keeps recurring across
every product and every team.

## The hidden tool

Apply the probe: remove auth from an app → the app degrades (no one can get in).
Add auth → the app evolves (users can be onboarded). Auth is therefore a *tool*
fused into the performance — see the fused-concern method
(`../framework/09-fused-concerns.md`).

Because the *same* auth integration repeats across every app, the integration
pattern is the hidden tool, not the app itself.

## The open layer

Extract auth as an open layer that applications attach and detach on demand: a
shared auth service with the user free not to know what happens inside
(`../framework/10-glossary.md` — Tool). Open it with a permissive license so no
one can re-close it (`../framework/08-license-enforcement.md`).

## The money gate

The app stays sellable. Users pay for what the app *does* for them — the product,
the service, the specific job the performance does — not for the shared auth
plumbing. Auth (tool) is free; the app (performance) is the money gate.
