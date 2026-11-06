# dsh-ask-for-help

A two-sided prototype for "external software asks the agent team for help".

## Sides

- Resident side (package/ask-for-help.mjs): zero-dependency local HTTP peer; advertises /.well-known/link-interconnect.json, registers ask_for_help through tools.expose, writes tickets to inbox/, and exposes wait so a Lead session is woken when someone shouts.
- Kernel side: the ask_for_help tool contract (deliver the ticket immediately, never block the agent), plus reply/send paths that put the answer back into the original conversation.

## Ticket lifecycle

pending -> notified -> answered; tickets are JSON files under the state directory; wait exits with a typed report (new ticket / link down / provider trouble / turn error).

## License

MIT