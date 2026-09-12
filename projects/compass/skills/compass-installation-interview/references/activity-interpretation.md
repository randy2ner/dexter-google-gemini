# Customer Activity Interpretation

## Meaning

A Conversation, also called an Activity, is one coherent unit of meaningful customer work. It is not an email thread, Teams chat, meeting, message, or other source container.

Customer work is materially attributable to an identifiable customer relationship, outcome, commitment, or need. Internal analysis, preparation, escalation, coordination, or follow-through qualifies only when that customer connection is concrete. General administration, learning, exploration, and unrelated internal work do not become Activities.

## Boundaries and content

- Several messages, threads, chats, meetings, or direct user statements may support one Activity.
- One source container may support several Activities when it contains distinct customer work.
- Each Activity states what happened, why it matters to the customer, participating People, and one Effort or Parking Lot disposition.
- Include progress, decisions, risks, commitments, insights, outcomes, and next steps only when supported.
- Preserve minimized source context that distinguishes evidence from interpretation without retaining raw transcripts.
- Ask only when customer relevance, Activity boundaries, continuity, identity, or Effort placement remains materially ambiguous.

## Accurate last Activity

Set `lastActivityAt` to the newest reliable timestamp among the individual evidence items that qualify as meaningful customer work for that Activity:

```text
lastActivityAt = max(timestamp of each qualifying customer-work item)
```

Qualifying items may be messages, replies, meeting contributions, or explicit user-supplied work events. When useful, `startedAt` records the earliest qualifying item.

Never substitute:

- thread or chat creation or start time;
- generic container modification time;
- a recent unrelated, administrative, or non-customer message;
- retrieval or scan time;
- Markdown modification time;
- relationship maintenance or Daily Log time; or
- attention state.

Inspect item-level content and timestamps and follow available continuation or pagination within the approved scope. If timestamps are unavailable, conflicting, future-dated, timezone-ambiguous, or incompletely retrieved, do not assign a confident `lastActivityAt`. Report the coverage gap and leave recency unresolved.

Email and Teams chat capabilities are independent. Success with one source does not establish the other.