# Separation 2 — The ready user-management schema

## The repeated pattern

Every app that holds users needs the same schema — users, roles, sessions,
password resets. The schema pattern repeats across every database and every
product (raw "The Layer Model": the next tool in the database problem is the
schema).

## The hidden tool

Probe: remove the user schema → the app degrades (it cannot hold its users).
Add a good user schema → the app evolves. The schema is a tool, currently baked
inside each app instead of standing alone.

## The open layer

Release the user-management schema pattern as an open, reusable schema layer that
attaches to any database on demand. "Making schemas open source makes the tools
another layer to become open source" (raw "The Layer Model").

## The money gate

The business built on the data — what the app does with its users — is the paid
performance. The schema (tool) is free for everyone.
