# Separation 3 — Logging as an open layer

## The repeated pattern

Every service wires in logging/observability — capture events, errors, metrics.
The same plumbing repeats across every application.

## The hidden tool

Probe: remove logging → the service degrades (you cannot see what it does).
Add logging → the service evolves (it becomes operable). Logging is a tool fused
into the performance.

## The open layer

Extract logging as an open layer applications attach on demand — a shared
logging/observability tool, open so anyone can build on it.

## The money gate

The service's own output — the product, the data processed, the job done for the
user — is what is sold. Logging (tool) stays open and free.
