# The Separations Ledger

Proof by example. Each entry below is a real tool found by applying the Separation
Law to a case we keep repeating. Reading these shows the method working — it is
not the theory, it is the theory applied.

## How to read an entry

Every separation answers the same four questions:

1. **The repeated pattern** — what performance keeps recurring, across actors.
2. **The hidden tool** — the reusable thing fused inside that performance
   (probe: remove it → degrades; add it → evolves).
3. **The open layer** — the separated tool as its own open, shared layer.
4. **The money gate** — what remains as the paid performance, the doing.

Apply this to your own work. When you find a tool, propose it via the
[separation template](../.github/ISSUE_TEMPLATE/separation.yml) and we add it here.

## The entries

| # | Hidden tool | Open layer | Money gate (performance) | Entry |
|---|-------------|------------|--------------------------|-------|
| 1 | Auth sub-system embedded in every app | Open auth layer (attach/detach) | The app's own job done for the user | [01-auth.md](01-auth.md) |
| 2 | User-management schema baked into each app's DB | Open ready user-schema layer | The business built on the data | [02-user-schema.md](02-user-schema.md) |
| 3 | Logging/observability code wired into every service | Open logging layer | The service's own output | [03-logging.md](03-logging.md) |
| 4 | Payment handling fused into each product | Open payment/checkout layer | The product or service sold | [04-payments.md](04-payments.md) |
| 5 | Notification/email plumbing repeated in every app | Open notification layer | The product your users actually use | [05-notifications.md](05-notifications.md) |

## What to do with a tool you find

Separate it. Open it (a license makes it durable — see `../framework/08-license-enforcement.md`).
Keep the remaining performance as the money gate. Then propose it here.
